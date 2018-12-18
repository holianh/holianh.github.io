---
image: http://www.recursosweb.es/wp-content/uploads/2014/04/github-pages.jpg
instantfeedback: true
description: Hướng dẫn cấu hình và sử dụng Github Pages 
layout: post
title: Cấu hình và sử dụng Github Pages 
category: Website 
tags: website
keywords: github, github pages, website, blog 
---

Dùng github pages làm trang blog cá nhân. Cách cài đặt và cấu hình khá đơn giản.

<figure><img src="http://www.recursosweb.es/wp-content/uploads/2014/04/github-pages.jpg" alt="Hướng dẫn sử dụng github pages" title="Hướng dẫn sử dụng github pages"></figure>

<h3>Cài đặt Github pages </h3>


<h3>Cập nhật Pages</h3>
```
1. Tạo new repositiry. copy cái link để git:
	https://github.com/holianh/holianh.github.io.git
2. Clone Project:
	Vào trong "~/www" mở terminal ra chạy lệnh này:
	git clone https://github.com/holianh/holianh.github.io.git
3. Edit project files:
	(Viết bài, cập nhật pages,...)
4. cd to project: u@ta:~/www/holianh.github.io$ 
	Để cập nhật: Thêm mới/ Thay đổi:

	git config --global user.email "tuananhvxl@gmail.com"
	git config --global user.name "Tuấn Anh"

	git init
	git reset HEAD --keep

	git add -A

	git commit -m "Init"
	git status
	
	git push -u origin master
	(Nhập username và pass)
	
	Nếu xóa file, thay: git add -A bằng: git rm <tên gile>
```

Xong!
