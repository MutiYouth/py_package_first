# This is a test package project.

This is a simple example package. You can use
[Github-flavored Markdown](https://guides.github.com/features/mastering-markdown/)
to write your content.


## 生成wheel文件
```bash
pip install wheel
python setup.py bdist_wheel
```
之后会在 `dist`目录下生成类似的文件: `name-x.x.x-py3-none-any.whl`


## 上传到pypi
现在已经可以使用该whl文件本地安装了，也可以传到 pypi 供所有人使用。

•	首先要注册个账号
•	然后安装twine
•	上传

```
# 1. Generating distribution archives
pip install twine
# python -m pip install --user --upgrade setuptools wheel

# 生成whl
python setup.py sdist bdist_wheel


# 2. 在用户名下创建用户验证文件(C:\Users\YOUR_USER_NAME\.config) (这一步好像没有用)
文件内容如下
-------------------------------
[distutils]
index-servers=pypi
 
[pypi]
repository = https://upload.pypi.org/legacy/
username = xxxx
password = xxxx
-------------------------------

# 3. 注册包 (可忽略，这一步现在非必须了)
python setup.py register

# 4. Uploading the distribution archives
# python -m pip install --user --upgrade twine
python -m twine upload --repository-url https://upload.pypi.org/legacy/ dist/*


# 5. 升级发布包
编写完成后，删除dist 目录，重新生成可发布的文件。然后验证和重新发布上传。


```



## 安装、卸载方式
```bash
# 源码方式
python setup.py install
# 在线安装方式
pip install lib_name
# 升级安装方式
pip install --upgrade lib_name

# 卸载
pip unintall lib_name
```

## REF
* onenote: 0124 python packagings
