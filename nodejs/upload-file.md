# Upload File


## Axios

```js
import axios, { post } from 'axios';

...

fileUpload(file) {
  const url = 'http://localhost:4000/file-upload';
  const formData = new FormData();
  formData.append('file',file)
  const config = {
    headers: {
      'content-type': 'multipart/form-data'
    }
  }

  return  post(url, formData, config);
}
```



## NodeJS

```js
const storage = multer.diskStorage({
  destination: function (req, file, cb) {
    cb(null, 'uploads/');
  },
  filename: function (req, file, cb) {
    console.log(file.originalname);
    console.log(file.fieldname);
    cb(null, file.fieldname + '-' + Date.now());
  }
});
const upload = multer({storage: storage});

...

const formData = new FormData();
formData.append('file', file);
axios.post('/file-upload', upload.single('file'), {headers: headers})
  .then(response => {
    console.log(response);
  })
  .catch(e => {
    console.error(e);
  });
```

- [Source](https://stackoverflow.com/questions/41878838/how-do-i-set-multipart-in-axios-with-react)
- [Source](https://www.npmjs.com/package/multer)
- [Source](https://dev.classmethod.jp/server-side/node-express-multer-file-upload/)
