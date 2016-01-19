# hello-github


Start to ust github.


# Note

## emacs.d

guru-mode 是用来修改键绑定用另外的替代的包。

rainbow-delimiters 是用来在 Lisp 的模式里分层级显示括号颜色，所有 Lisp 模式都这样。

ido 是用来在 buffer 里搜索文件的。 类似的还有 anything。

helm 是一个 Emacs incremental and narrowing framework。 fork from anything。

company 是一个补全框架。





# design of my app

Here record all the app's design documents written by myself. From design to complete.

## Peachblossom -- My Emacs config




## Phoenix -- A fixed assets management system

Development code: __Phoenix__ 

It is a website to manage the IT fixed assets, It is wrote in PHP with Laravel 5 frame and run on Apache. Use MySQL to store data.


### Used tools

* Apache 2
* PHP 7
* Laravel 5
* Bootstrap 3
* Opera explorer CSS
* MySQL 5.7




### Structure 


### Database 

#### Table

* assets
* users



#### SN code rule



## Cherry -- An accounts book


Development code: __Cherry__

It is an accounts book written in pure Win32 API, use to store the username and password on every website.

### Features

* Search by pinyin, short pinyin, and Chinese words
* Save password with md5 and random salt
* Encrypt SQLite 3 database file with AES 128bit
* Export to html/txt format
* English/Chinese UI



### Used tools

* Win32 API
* SQLite 3
* Crypt library from OpenSSL
* A pinyin dictionary of GBK from Internet 




### Structure


### Database

#### Table 

Only one table: accounts


| field name |      id     |       tag       | category |      url       |   user  | password |      note      |       lastmod       | pyshort | pyfull |
|------------|-------------|-----------------|----------|----------------|---------|----------|----------------|---------------------|---------|--------|
| type       | integer     | text            | text     | text           | text    | text     | text           | nowtime             | text    | text   |
| property   | primary key | unique not null |          |                |         |          |                | not null default    |         |        |
| value      | 1,2,3       | Google          | www      | www.google.com | ruoshui | mima     | google account | 1990-02-14 14:21:03 | google  | google |
| length     | auto        | 20              | 20       | 200            | 100     | 16       | 200            | 20                  | 20      | 100    |



#### SQL

* Create table

```sql
create table accounts(id integer primary key, tag text unique not null, category text, url text, user text, password text, phone text, mail text, note text, lastmod TimeStamp NOT NULL DEFAULT (datetime('now','localtime')), pyshort text, pyfull text);

```

* Insert data

```sql
insert into accounts (tag, category, url, user, password, phone, mail, note, pyshort, pyfull) 
    values("tag" "category" "url" "user" "password" "phone" "mail" "note" "pyshort" "pyfull");
```


* Update data
```sql
update accounts set category="category" url="url" user="user" password="password" phone="phone" 
    mail="mail" notes="notes" lastmodified="datetime('now','localtime')" where tag="tag";
```


* Delete data







