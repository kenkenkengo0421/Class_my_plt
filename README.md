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

#ヒストグラム 
#ヒストグラム( sns)
#KDEプロット 
#文字列の値をカウント(棒グラフ)
#折れ線グラフ
#折れ線グラフ複数の項目


#ヒストグラム
Hist(data=<DF>, column_name=<DFのcolumn>, bins=<bins>, figsize=(<横大きさ,縦大きさ>), step=<区切り>)

#ヒストグラム ( snsバージョン )
sns_Hist(data=<DF>, x=<横軸>, hue=<基準のcolumn>, figsize=(<横大きさ,縦大きさ>), step=<区切り>)

#KDEプロット(滑らかなヒストグラム)
sns_kde(data=<DF>,
        x=<横軸>,
        hue=<基準のcolumn>,
        fill=<True>,                    #塗りつぶすかどうか
        common_norm=<False>,　　　　　　 #よくわからん 
        figsize=(<横大きさ,縦大きさ>),
        step=<区切り>)

#文字列の値をカウント(棒グラフ)
sns_countplot(data=<df>,
              x=<DFのcolumn>,
              hue=<基準のcolumn>,
              figsize=(<横大きさ,縦大きさ>),
              y_step=<区切り>)


#折れ線グラフ
sns_line(df, x='step', y='money', step=100)

#折れ線グラフ複数の項目
cols_to_plot = [
    'money', 
    'wheat_price', 
    'melon_price', 
    'wheat_in_shed', 
    'melon_in_shed'
]

sns_line_s(df, x='step', y=cols_to_plot, step=30)

```





