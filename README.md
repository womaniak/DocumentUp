### 1) Install NPM
#### Link: <a href="https://nodejs.org/en/" target="_blank">Node package manager</a>
##### 1.1) After installing run in cmd:
``` js
>npm install gulp -g
```
<sup>-g means global so it can be referenced to from anywhere with cmd.

### 2) Creating a Gulp Project
##### 2.1) Navigate to folder using:
``` js
>cd c:/folder/subfolder/
```
##### 2.2) Then create a new project using npm
``` js
>npm init
```
<sup>The npm init command creates a package.json file for your project

##### 2.3) Install Gulp in project
``` js
>npm install gulp --save-dev
```
<sup>We've added --save-dev, which tells the computer to add gulp as a dev dependency in package.json

##### 2.4) Create gulpfile.js
>Either manually create a gulpfile.js file in the chosen folder and paste in "var gulp = require('gulp');"

Or run the code below from within the chosen folder with cmd:
``` js
>echo var gulp = require('gulp'); >> gulpfile.js
```
<sub>

### 3) Gulp sass & watch
#### 3.1) Create gulp sass task
Paste the code below in the gulpfile.js after "var gulp = require('gulp');"
``` js
var sass = require('gulp-sass');

gulp.task('sass', function(){
  return gulp.src('/*.scss') //Source file
    .pipe(sass()) // Using gulp-sass
    .pipe(gulp.dest('/')) // Destination of the output file
});
```

#### 3.2) Test
Create a test .scss file with the content form below
``` js
// styles.scss
.testing {
  width: percentage(5/7);
}
```

#### 3.3) Gulp watch
Add the following task to the gulpfile.js at the end of the file:
```js
gulp.task('watch', function(){
  gulp.watch('app/scss/**/*.scss', ['sass']); //Source of the file
  // Other watchers go here
})
```
<sup> Add multiple file sources below the first gulp.watch

##### To start Gulp Watch just run the command below in CMD
<sup> *note that cmd has to be navigated to the same folder as gulpfile.js
``` js
>gulp watch
```
