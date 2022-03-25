# Blog_Meida

#### 介绍


云海Blog：http://blog.shaiol.cn



#### 说明

用户存储图片，博客使用的图床

# 使用规范
> 每个目录对应不同分类下文章
## /img
过去未规范化使用的图片存储路径，日后再做整理

## /java
Java分类下文章的图片所使用的路径

## /wechat
微信小程序

### /wechat/cloudDev
微信小程序云开发

## /skill
技术分类下文章的图片所使用的路径

## ....

## Gitee和Github链接对照
https://raw.githubusercontent.com/whjysh/Images/master/   xxx.png

https://gitee.com/ushai/yunhaiblog/raw/master/            xxx.png


# 图床迁移方案
连带路径迁移更改主路径
采用数据库`update`语句

```sql
UPDATE wp_posts 
	SET post_content = REPLACE ( post_content, 
                                'https://gitee.com/../master/', 
                                'https://raw.githubusercontent.com/.../master/' ) 

WHERE
	post_content LIKE '%https://gitee.com/../master/%'
```
