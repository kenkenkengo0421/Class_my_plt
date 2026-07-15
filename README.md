# グラフ描画用ライブラリ

```
project
      |_main.ipynb
      |_my_plot.py
      |_data
           |_train.csv
```


```py
main.ipynb---

from my_plots import Hist, sns_Hist

df = pd.read_csv("data/train.csv")

#1
Hist(df, column_name="bmi", step=2)

#2
sns_Hist(df, x="bmi", hue="health_condition", step=1)

#3
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

