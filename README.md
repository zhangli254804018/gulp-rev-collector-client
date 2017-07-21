### Works with gulp-rev-collector

- [gulp-rev](https://github.com/sindresorhus/gulp-rev)
- [gulp-rev-collector](https://github.com/shonny-ua/gulp-rev-collector) - Static asset revision data collector

本插件為個人研發調整代碼適應項目使用使用前請確認好該插件依賴為:



做出以下調整

```
var collector = require('gulp-rev-collector-client);
gulp.task('rev', function() {
    return gulp.src(['rev/**/*.json', 'templates/**/*.php'])
        .pipe(revCollector({
            '../css/': 'css/',
            '../js/': 'js/',
            // 默認為false 壓縮後綴為 ./css/main.min.css?v=1e2c45287b
	        // 如為true 壓縮後綴為 ./css/main.min.1e2c45287b.css
            hash:true
        }))
        .pipe(gulp.dest(''));
});

```