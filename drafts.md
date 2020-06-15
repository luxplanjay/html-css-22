# Директива @if

```scss
/*
* Дефолтный размер и не окружность по умолчанию
*/
@mixin avatar($size, $circle: false) {
  width: $size;
  height: $size;

  @if $circle {
    border-radius: 50%;
  }
}
.avatar {
  background-color: #ccc;
  border: 2px solid #2a2a2a;
  @include avatar(100px);
}

.avatar--round {
  @include avatar(150px);
}
```

# Директива @if/else

```scss
$light-background: #f2ece4;
$light-text: #036;
$dark-background: #6b717f;
$dark-text: #d2e1dd;

@mixin theme-colors($light-theme: true) {
  @if $light-theme {
    background-color: $light-background;
    color: $light-text;
  } @else {
    background-color: $dark-background;
    color: $dark-text;
  }
}

body.light-theme {
  @include theme-colors($light-theme: true);
}

body.dark-theme {
  @include theme-colors($light-theme: false);
}
```