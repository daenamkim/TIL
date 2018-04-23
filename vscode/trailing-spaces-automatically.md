# Trailing Spaces Automatically

I wanted to trail all spaces automatically and then there is a simple solution.

Go to _**Preferences(基本設定) > User Settings(設定)**_ and add below.

```json
{
    ...
    "files.trimTrailingWhitespace": true
}
```

But there is a better extension called [Trailing Spaces]((https://marketplace.visualstudio.com/items?itemName=shardulm94.trailing-spaces)) for VS Code.
Instead of the setting above add below then spaces in the end of line will be shown and removed after save. Cool.

```json
{
    ...
    "trailing-spaces.trimOnSave": true,
}
```

[StackOverflow](https://stackoverflow.com/questions/30884131/remove-trailing-spaces-automatically-or-with-a-shortcut)
[Trailing Spaces](https://marketplace.visualstudio.com/items?itemName=shardulm94.trailing-spaces)
