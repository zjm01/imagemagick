# 安装
cnpm install --save imageMagick gm  （我用npm会报错，安装不成功）
## imageMagick有愈多命令行来操作图片，也留出来了许多编程接口，比如java,php，node等  
# 命令行
## 转换图片格式
magick rose.jpg rose.png（将jpg格式转化为png；也可以是pdf转图片）  
# 转化为其他格式同时改变图片大小
magick rose.jpg -resize 50% rose.png  

# node中使用
var fs, gm;  
 gm = require('gm');  
//  改变图片大小   
 gm('../images/cat.jpg').options({  
   imageMagick: true   
 }).resize(130, 105).write('../images/after.jpg', function(err) {  
   if (err) {  
     return console.error(err);   
   }  
   return console.log('success');  
 });          
// 将pdf格式转化为图片     
 gm('../images/lanting.pdf').options({   
   imageMagick: true   
 }).command("convert").in("-density", "500").write('../images/lanting1.jpg', function(err) {   
   if (err) {   
     return console.error(err);   
   }
   return console.log('success');   
 });  
