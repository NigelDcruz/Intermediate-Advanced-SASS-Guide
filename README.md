# Intermediate to Advanced SASS/SCSS Guide

## Control directives

Control directives are an advanced feature, and are uncommon in day-to-day styling. They exist mainly for use in mixins, particularly those that are part of libraries.

Note:  
```
// This is the syntax that must be followed while using variables with selectors

#{$variable_name}

//Example

$sass-success: "success";

p.#{$sass-success}{
  color: green;
}

/* compiled CSS */
p.success{
  color: green;
}

```
### @if

```
$mobile: false; //Declare Value

article {

    width: 300px;
    color: #000;
    
    @if ($mobile) { // Will execute only for moblie devices
        width: 300px;
    }
}

```
### @else if

```
$type: monster;

p {
  @if $type == ocean {
    color: blue;
  } @else if $type == matador {
    color: red;
  } @else if $type == monster {
    color: green;
  } @else {
    color: black;
  }
}

```

### @each

```
@each $name in 'save' 'cancel' 'help' {
    .icon-#{$name} {
        background-image: url('/images/#{$name}.png');
    }
}


/* compiled CSS */
.icon-save {
  background-image: url("/images/save.png");
}
.icon-cancel {
  background-image: url("/images/cancel.png");
}
.icon-help {
  background-image: url("/images/help.png");
}

```
#### Note: For Detailed Explanation, Please check out the official SCSS Documentation http://sass-lang.com/documentation/file.SASS_REFERENCE.html
