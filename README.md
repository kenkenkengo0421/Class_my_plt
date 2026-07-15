# グラフ描画用ライブラリ

# 環境構築（テスト用）

<details><summary></summary>

cloneする
```PowerShell
git clone https://github.com/kenkenkengo0421/my_plt_class.git

```

<br>

venv構築
```PowerShell
py -m venv .venv
```

<br>

venv有効化
```PowerShell
.\.venv\Scripts\Activate.ps1
```

<br>

必要pipinstall
```PowerShell
pip install -r requirements.txt
```

<br>

nb起動
```PowerShell
jupyter lab
```




</details>



# 使用例、以下の構成の場合

```
project
      |_main.ipynb
      |_【my_plot.py】←-------class file
      |_data
           |_train.csv
```

<br>

### [main.ipynb](https://github.com/kenkenkengo0421/my_plt_class/blob/main/main.ipynb)
### [my_plot.py](https://github.com/kenkenkengo0421/my_plt_class/blob/main/my_plot.py)

<br>

```py
main.ipynb---

from my_plots import Hist, sns_Hist

df = pd.read_csv("data/train.csv")

#1ヒストグラム
Hist(df, column_name="bmi", step=2)

#2ヒストグラム ( sns)
sns_Hist(df, x="bmi", hue="health_condition", step=1)

#3KDEプロット(滑らかなヒストグラム)
sns_kde(df, x='calorie_expenditure',hue='health_condition',
        step=200,figsize=(10,5)
       )
```




# ヒストグラム#1
```py
Hist(data=<DF>,
	 column_name=<DFのcolumn>,
	 bins=<bins>,
	 figsize=(<横大きさ,縦大きさ>),
	 step=<区切り>)
```

# ヒストグラム ( sns)#2
```py
sns_Hist(data=<DF>,
		 x=<横軸>,
		 hue=<基準のcolumn>,
		 figsize=(<横大きさ,縦大きさ>),
		 step=<区切り>)
```

# KDEプロット(滑らかなヒストグラム)#3
```py
sns_kde(data=<DF>,
        x=<横軸>,
        hue=<基準のcolumn>,
        fill=<True>,                    #塗りつぶすかどうか
        common_norm=<False>,　　　　　　 #よくわからん 
        figsize=(<横大きさ,縦大きさ>),
        step=<区切り>)
```

