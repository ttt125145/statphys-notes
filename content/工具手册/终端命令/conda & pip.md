*conda源*
```
conda config --add channels               添加源
conda config --remove-key channels        删除源
conda info                查看配置信息(源,包和环境储存位置等)

```

*conda虚拟环境*
```
conda env remove -n 环境名 #删除环境

conda env list     #查看虚拟环境
```

*pip虚拟环境*

```

python -m venv 环境名	创建虚拟环境

环境名\Scripts\activate	激活虚拟环境

python.exe -m pip install --upgrade pip 	更新pip

pip freeze > requirements.txt  导出库名列表
pip install -r requirements.txt  按库名列表下载库

decativate		关闭虚拟环境

```

