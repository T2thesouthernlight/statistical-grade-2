## 0. Follow up
  組み合わせ計算<br>
  共分散の計算<br>
  確率変数に関する計算<br>
  母比率計算<br>
  ｔ検定<br>
  重回帰分析全般（ｔ値、ｐ値、Ｒ２、Ｒ２（修正済み）、有意性など）<br>
  χ二乗検定<br>
  標本比率<br>
  抽出方法<br>

## 1. データの記述と要約
  |名前|数式または記号|説明|関連|
  |:--:|:--|:--|:--|
  |||||
  |||||
  |||||
  |||||
  |相関係数|<img src="https://latex.codecogs.com/svg.latex?r_{xy} = \frac{S_{xy}}{S_x S_y}" height="40"/><p> <img src="https://latex.codecogs.com/svg.latex?S_{xy}" height="20"/> は共分散<br> <img src="https://latex.codecogs.com/svg.latex?S_{xy} = \frac{1}{n} \sum_{i=1}^{n} (x_i - \bar{x})(y_i - \bar{y})" height="45"/> <p> <img src="https://latex.codecogs.com/svg.latex?S_x" height="20"/>は<img src="https://latex.codecogs.com/svg.latex?x" height="10"/>の標準偏差<p><img src="https://latex.codecogs.com/svg.latex?S_y" height="20"/>は<img src="https://latex.codecogs.com/svg.latex?y" height="12"/>の標準偏差|データ<img src="https://latex.codecogs.com/svg.latex?x" height="10"/>と<img src="https://latex.codecogs.com/svg.latex?y" height="12"/>の相関をみることができる<p>必ず<img src="https://latex.codecogs.com/svg.latex?-1 \leqq r_{xy} \leqq 1" height="20"/>の値を取る||
  |偽相関||見かけ上の相関、関係性がないのに相関があるように見えること||
  |偏相関係数|<img src="https://latex.codecogs.com/svg.latex?r_{(yz.x)} = \frac{r_{yz} - r_{xy} r_{xz}}{\sqrt{1 - r_{xy}^2} \sqrt{1 - r_{xy}^2}}" height="45"/>|偽相関を見抜く方法<p>データ$x$、$y$、$z$があったときに$x$による相関の影響を除く||
  |独立性と無相関||独立性なら無相関とう関係は成り立つが、無相関なら独立<br>という関係は成り立たない<p>例として、無相関であるプロットを見たときに明らかに独立で<br>ないケース（関係性がある）<p>以下の例だと、相関係数が0.04だけど、明らかに独立ではない<br><img src="image-16.png" width="300px">||
  |||||
  |||||
  |ラスパイレス指数|<img src="https://latex.codecogs.com/svg.latex?P_L = \frac{\sum_{i=1}^{n} p_{it} q_{0i}}{\sum_{i=1}^{n} p_{0i} q_{0i}} \times 100" height="45"/><p>$p_{0i}$：基準年の価格<br>$q_{0i}$：基準年の数量<br>$p_{ti}$：比較年の価格<br>$q_{ti}$：比較年の数量|基準年の購入量や取引量を重みとして算出する価格指数<p>基準年の値を基準として計算して比較する<p>基準年と比べてどれだけ、変化したかを表す||
  |パーシェ指数|<img src="https://latex.codecogs.com/svg.latex?P_P = \frac{\sum_{i=1}^{n} p_{it} q_{ti}}{\sum_{i=1}^{n} p_{0i} q_{ti}} \times 100" height="45"/><p>$p_{0i}$：基準年の価格<br>$q_{0i}$：基準年の数量<br>$p_{ti}$：比較年の価格<br>$q_{ti}$：比較年の数量|比較年の購入量や取引量を重みとして算出する価格指数<p>比較年の値を基準として計算して比較する<p>基準年の価格で同じものを購入した場合の費用を計算||
  |フィッシャー指数|<img src="https://latex.codecogs.com/svg.latex?\sqrt{P_L \times P_P}" height="25"/>|ラスパイレス指数とパーシェ指数の幾何平均によって算出<p>理想的な指数とされているが計算が複雑||
  |||||
  |||||
  |変化率（時系列データ）|差を使う場合<br>$$\text{ある時点の値} - \text{前時点の値}$$<p>比を使う<br>$$\text{ある時点の値} \div \text{前時点の値}$$<p>変化率<br>$$(\text{ある時点の値} - \text{前時点の値}) \div \text{前時点の値}$$|差：どの程度増加・現象したかがわかる<p>比：前の時点と比較して何倍増加したかわかる<p>変化率：前の時点に対するある時点の値の増減の度合いがわかる||
  |||||
  |||||
  |||||
  |||||
  |||||
  |||||

## 2. 確率と確率分布
  |名前|数式または記号|説明|関連|
  |:--:|:--|:--|:--|
  |試行||||
  |根元事象||試行によって起こりうる個々の結果<br>素事象、標本点ともいう||
  |全事象|$$\Omega$$|すべての根元事象の集合、標本空間ともいう||
  |和事象|$$A_1 \cup A_2$$|少なくとも$A_1$もしくは$A_2$の１つが起こる||
  |積事象|$$A_1 \cap A_2$$|$A_1$と$A_2$が同に起こる||
  |空事象|∅|何も起こらない事象||
  |確率の公理||1. 事象Aに対して$0 \leqq P(A) \leqq 1$を取る<br>2. $P(\Omega) = 1$<br>3. $A_1$, $A_2$,,,が互いに排反ならば<br>$P(A_1 \cup A_2 \cup ,,,) = P(A_1) + P(A_2) + ,,,$となる<br>コルモゴロフの公理ともいう||
  |独立性|$P(B \| A) = P(B)$, $P(A \| B) = P(A)$<br>$P(A \cap B) = P(A)P(B)$|一方の事象が起こるかどうかが他方の事象の<br>起こる確率に影響しないこと<br>二つの確率がある場合でお互いの<br>結果が互いに影響しない場合は<br>**互いに独立**という||
  |排反|<img src="image-5.png" width="300px">|2つの事象AとBが同時に起こらない場合、つまり排反事象の場合の確率||
  |一般的な確率|<img src="https://latex.codecogs.com/svg.latex?P(A) = \frac{A}{\Omega}" height="30"/>|Aは起こった事象の数<br>$\Omega$は全事象<br>古典的な定義でありラプラス<br>の定義ともいう||
  |期待値|<img src="https://latex.codecogs.com/svg.latex?E(x) = \sum_{k=1}^{n}p_k x_x" height="40"/>|pは確率<br>xは取りうる値<br>1回の試行で得られる値の平均値のことで||
  |加法定理 1|<img src="https://latex.codecogs.com/svg.latex?P(A \cup B) = \frac{(A) + (B)}{\Omega}" height="40"/>|$A \cap B =$ ∅の場合|
  |加法定理 2|<img src="https://latex.codecogs.com/svg.latex?P(A \cup B) = (A) + (B) - P(A \cap B)" height="40"/>|$A \cap B \neq$ ∅の場合|
  |条件付き確率|<img src="https://latex.codecogs.com/svg.latex?P(B\|A) = \frac{P(A \cap B)}{P(A)}" height="40"/> <br> <img src="https://latex.codecogs.com/svg.latex?P(A \cap B) = P(B\|A)P(A)" height="20"/>|Aという条件下でBが起こる確率|乗法定理|
  |乗法定理|<img src="https://latex.codecogs.com/svg.latex?P(A \cap B) = P(B\|A)P(A)" height="20"/>||条件付き確率|
  |ベイズの定理|<img src="https://latex.codecogs.com/svg.latex?P(H_i\|A) = \frac{P(H_i \cap A)}{P(A)}" height="40"/> <br> <img src="https://latex.codecogs.com/svg.latex?P(H_i \| A) = \frac{P(H_i)P(A\|H_i)}{P(A)}" height="40"/>|原因から結果を探る手法<br>P(A)は事前確率<br>$P(H_i\|A)$は事後確率||
  |離散型確率分布||<img src="image.png" width="300px">|一様分布<br>二項分布<br>多項分布<br>ポアソン分布<br>幾何分布<br>超幾何分布|
  |確率変数||変数Xのことである確率に対して取り得る値||
  |確率関数||<img src="https://latex.codecogs.com/svg.latex?f(x_i)" height="20"/>と表わされる<br>離散型の場合は<img src="https://latex.codecogs.com/svg.latex?0 \leq f(x_i) \leq 1" height="20"/> となり<br>連続型の場合は <img src="https://latex.codecogs.com/svg.latex?\sum_{i=1}^{\infty}f(x_i) = 1" height="40"/>となる||
  |確率質量関数|<img src="https://latex.codecogs.com/svg.latex?f(x)=P(X=x)" height="20"/> <br> <img src="https://latex.codecogs.com/svg.latex?\sum_{i=1}^{n}P(X=x_i)=1" height="35"/> |すべてを足し合わせると１になる||
  |連続型確率分布|<img src="https://latex.codecogs.com/svg.latex?P(X=x) = \frac{1}{\infty}" height="20"/> |取りうる値に切れ目がないため、無限となる<br><img src="image-1.png" width="300px">|連続一様分布<br>正規分布<br>指数分<br>t分布<br>F分布<br>カイ二乗分布|
  |確率密度関数|<img src="https://latex.codecogs.com/svg.latex?P(a \leq X \leq b) = \int_{a}^{b} f(x) dx" height="20"/> |算出される値は面積を表していて、その値が確率となる<br>また、**1を超えることがある**<br>連続型確率変数ともいう||
  |累積分布関数|離散型<br> <img src="https://latex.codecogs.com/svg.latex?F(x) = P(X \leq x) = \sum_{X \leq x} P(X)" height="20"/> <p><p>連続型<br> <img src="https://latex.codecogs.com/svg.latex?F(x) = P(-\infty \leqq X \leqq x) \\ = \int_{-\infty}^{x}f(t)dt" height="20"/>|確率変数$X$が**ある値$x$以下 <img src="https://latex.codecogs.com/svg.latex?(X \leq x)" height="20"/>の値となる確率**<p> 大文字のFを用いてF(x)と表わす<p>離散型<br><img src="image-12.png" width="300px"> <p><p> 連続型<br><img src="image-13.png" width="300px"><p><p> 確率密度関数$f$ <--> 累積分布関数$F$と<br>表わされる<p><p> <img src="https://latex.codecogs.com/svg.latex?F(\infty)=1" height="20"/><br>確率変数がある範囲の値しかとらないときに、$X$がとる値がその範囲の最大値以上となる場合に成立する<p><p> <img src="https://latex.codecogs.com/svg.latex?F(-\infty)" height="20"/> <br>確率変数$X$がとる値がマイナス無限大となる確率は0である||
  |期待値|離散型<br> <img src="https://latex.codecogs.com/svg.latex?E[X] = \sum_i x_if(x_i) = \mu" height="20"/> <p>連続型<br> <img src="https://latex.codecogs.com/svg.latex?\int_{-\infty}^{\infty}x(fx)dx = \mu" height="20"/> |平均と同じ意味||
  |分散|離散型<br> <img src="https://latex.codecogs.com/svg.latex?V[X] = E[(X-\mu)^2] \space = \sum_i(x_i - \mu)^2f(x_i) \space = \sigma^2" height="35"/> <p>連続型<br> <img src="https://latex.codecogs.com/svg.latex?V[X] = E[(X-\mu)^2]" height="35"/> <br> <img src="https://latex.codecogs.com/svg.latex?= \int_{-\infty}^{\infty}(x-\mu)^2f(x)dx \space = \mu^2" height="35"/> <p>また。。。<br> <img src="https://latex.codecogs.com/svg.latex?V[X] = E[X^2] - \mu^2" height="35"/> <br>としても定義される|バラつきを表す指標となり標準偏差 <img src="https://latex.codecogs.com/svg.latex?\sigma" height="20"/> の2乗||
  |モーメント|歪度（わいど）<br> <img src="https://latex.codecogs.com/svg.latex?\frac{n}{(n-1)(n-2)} \sum_{i=1}^{n}(\frac{x_i-\bar{x}}{s})^3" height="30"/> <br><br>尖度（せんど）<p> <img src="https://latex.codecogs.com/svg.latex?\frac{n(n+1)}{(n-1)(n-2)(n-3)}\sum_{i=1}^{n}\frac{(x_i-\bar{x})^4}{s^4}-\frac{3(n-1)^2}{(n-2)(n-3)}" height="30"/> |歪度と尖度で表される<p>歪度（わいど）<br>分布が正規分布からどれだけ歪んでいるかを表す統計量で、<br>左右対称性を示す指標のことです。サンプルサイズをn、<br>各データの平均値を、標準偏差をsとすると歪度は次の式から求めらる<br><img src="image-2.png" width="500px"><p>尖度（せんど）<br>分布が正規分布からどれだけ尖っているかを表す統計量で、<br>山の尖り度と裾の広がり度を示します。サンプルサイズをn、<br>各データの平均値を、標準偏差をsとすると尖度は次の式から求められます。<br><img src="image-3.png" width="500px">||
  |ベルヌーイ分布|$P(X=1) \equiv f(1) = p$<br>$P(X=0) \equiv f(0) = 1-p$<p><p>期待値<br>$\mu = E[X] $<br>$= 1 \times p + 0 \times (1-p) = p$<p><p>分散<br>$\sigma^2 = E[X^2] - \mu^2$<br>$= 1^2 \times p + 0^2 \times (1-p) - \mu^2$<br>$= p(1-p)$|ある確率に応じた１か０かの二つの値をとる<br>$0 \leq p \leq 1$の範囲となる||
  |二項分布|$$P(X=x) = f(x) \space = _nC_xp^x(1-p)^{n-x}$$ <p><p> 期待値<br>$$E[X] = np$$<br>$$ = \sum_{x=0}^{n}x \frac{n!}{x!(n-x)!} p^x(1-p)^{n-x}$$<p><p>分散<br>$$V[X] = np(1-p) \\ = E[X(X-1)] + E[X]-(E[X])^2 \\ = n(n-1)p^2+np-(np)^2$$|成功率pのn回ベルヌーイ試行を行ったとき、<br>成功回数がxとなる確率<p>$$B(n,p)$$と記すこともある||
  |ポアソン分布|$f(x) = \frac{e^{-\lambda}\lambda^{x}}{x!}$<p><p>期待値<br>$E[X] = \lambda$<p><p>分散<br>$V[E] = \lambda$|$Po(\lambda)$<br>ここで$np$を一定の値「$\lambda$（ラムダ）」とおき、<br>$np = \lambda$のままで$n$を十分大きく$p$を十分に小さくした<br>場合の二項分布は、平均 $\lambda$のポアソン分布に近似すること<br>ができます。<p>「ある期間に平均$ \lambda $ 回起こる現象が、ある期間に$X$回起きる確率の分布」||
  |幾何分布|$P(X=k) = (1-p)^{k-q}p$ ($k$ = 1,2,3,...)<p><p>期待値<br>$E(X) = \frac{1}{p}$<p>分散<br>$V(X) = \frac{1-p}{p^2}$|成功確率がpである独立なベルヌーイ試行を<br>繰り返す時、初めて成功するまでの試行回数Xが<br>従う分布である。<br>幾何分布の無記憶性、ある事象が発生する確率は、<br>その事象がはっせいする前の情報の影響を受けない||
  |超幾何分布|$$ P(X=k) = \frac{_{N}{C}_{k} \times _{N-M}{C}_{n-k}}{_{N}C_n} $$<p>k以下の条件を満たす<br>$$\max (0, n-(N-M)) \leq k \leq \min (n, M)$$<p>期待値<br>$$E(X) = np \space \frac{M}{N}$$<p>分散<br>$$V(X) = n . \frac{M(N-M)}{N^2} . \frac{N-n}{N-1}$$|AとBで構成されるN個からなる集団があり、AがM個、<br>BがN-M個であるとします。この集団から取り出された<br>n個の中に含まれるAの個数が従う確率分布||
  |負の二項分布|1.<br>$$P(X=x) =_{k+x-1}C_{x}p^{k}(1-p)^{x}$$ <br> $$(k = 1,2,3,...)$$ <p> 期待値<br> $$E(X) = k \frac{1-p}{p}$$ <br>分散<br> $$V(X) = k \frac{1-p}{p^2}$$<p><p>2.<br> $$P(X=x) = _{x-1}C_{k-1} p^{k}(1-p)^{x-k}$$ <br> $$(k = 1,2,3,...)$$<br>期待値<br>$$E(X) = \frac{k}{p}$$<br>分散<br>$$V(X) = k \frac{1-p}{p^2}$$|1.<br>成功率がpである独立なベルヌーイ試行を繰り返す時、<br>**k回成功するまでの失敗回数Xが従う分布**<p><p>2.<br>成功率がpである独立なベルヌーイ試行を繰り返す時、<br>**k回成功するまでの試行回数Xが従う分布**||
  |正規分布|$f(x) = \frac{1}{\sqrt{2 \pi \sigma }}e^ {-\frac{(x - \mu)^2}{2 \sigma^2}}$<br>$(-\infty \lt x \lt \infty)$<p>もしくは<p>$f(x) = \frac{1}{\sqrt{2 \pi \sigma }}\exp(-\frac{(x - \mu)^2}{2 \sigma^2})$<br>$(-\infty \lt x \lt \infty)$<p>期待値<br>$E(X) = \mu$<p>分散<br>$V(X) = \sigma^2$|統計学における検定や推定、モデルの作成など様々な<br>場面で活用される連続型確率分布<br>横軸を確率変数を、縦軸はそのときの確率密度を表す<p><img src="image-4.png" width="300px"><br>**平均$\mu$、分散$\sigma^2$に従う正規分布**といい、**$X \text{～} N(\mu,\sigma^2)$**<p>**再生性**<br>正規分布$N(\mu_1,\sigma_{1}^{2})$に従うあるデータと、そのデータとは<br>独立な別の正規分布$N(\mu_{2}, \sigma_{2}^{2})$に従うデータを足したデータは<br>、正規分布$N(\mu_{1} + \mu_{2}, \sigma_{1}^{2}+\sigma_{2}^{2})$に従う<p>標準正規分布への変換<br>正規分布の中で「平均$\mu = 0$、分散$\sigma^2 = 1$」である正規分布を<br>**標準正規分布**という、標準正規分布は$X～N(0,1)$と書く||
  |標準正規分布|標準化とは<br>$z = \frac{X - \mu}{\sigma}$<p><p>確率密度関数の算出<br>$F(x) = P(-\infty \leq X \leq x)$<br>$=\int_{- \infty}^{x}f(t)dt$<p>$f(t)$とは<br>$f(t) = \frac{1}{\sqrt{2\pi}}\exp(-\frac{t^2}{2})$|ある確率変数$X$が平均$\mu$、分散$\sigma^2$の**正規分布に従うとき**、<br>その確率変数$X$を標準化($z$化した平均$\mu = 0$、分散$\sigma^2 = 1$に<br>従う標準正規分布となる)することにより、**異なるデータ同市を<br>単純に比較できる。**<p>また、累積分布関数$F(x)$は確率密度関数$f(t)$を用いて算出できる。<br>ただし、毎回算出するのは面倒であるた、通常は**標準正規分布表**<br>から数値を参照する。||
  |指数分布|$f(x) =	\begin{cases} \lambda e^{-\lambda x} \space \space x \geqq 0 \\ 0 \space \space \space \space \space \space \space \space \space \space x \lt 0 \end{cases}$<p><p>期待値:<br>$E(X) = \frac{1}{\lambda}$<p><p>分散<br>$V(X) = \frac{1}{\lambda^2}$<p><p>$f(t) = \lambda e^{-\lambda t}$は確率密度関数,<br>特定の値の濃さ（密度）を連続分布としても使用<p><p>累積分布関数<br>$P(T \leq t) = 1-e^{-\lambda t}$<p><p>生存関数<br>$P(T \geq t)=e^{-\lambda t}$|ある事象が発生してから次に起こるまでの期間が従う分布<p>$\lambda =$**ある期間に事象が起こる回数**<p>$X = x$（確率密度関数）<p>**※必ず正の値を取る**<p><p>累積分布関数<br>$t$以下になる確率を求める時に使用<p><p>生存関数<br>$t$より大きい、まだ*"起こらない"*確率||
  |離散一様分|$P(X=k) = \frac{1}{N} (k=1,2,...,N)$<p>$E(X) = \frac{N + 1}{2}$<br>$V(X) = \frac{N^2 - 1}{12}$<p><p>別の例として。。。<br>$P(X=k) = \frac{1}{b-a+1} \space (k=a,a+1,...,b)$<br>$E(X) = \frac{a+b}{2}$<br>$V(X) = \frac{(b-a+1)^2-1}{12}$|すべての事象の起こる確率が等しい分布のこと<p><p><img src="image-6.png" width="300px">||
  |連続一様分布|$f(x) = \frac{1}{b-a} \space (a \leq x \leq b)$<br>$f(x) = 0 (x \lt a, x \gt b)$<br>$E(X) = \frac{a+b}{2}$<br>$V(X) = \frac{(b-a)^2}{12}$|確率変数が**X**がどんな値でも、その時の確率密度関数$ f(x) $が<br>**一定の値をとる分布のこと**<p><p><img src="image-7.png" width="300px">||
  |||||
  |||||
  |||||
  |２変数の確率、同時確率|離散型<br>$f(x_i , y_j) = P(X = x_i , Y = y_j) \\ (i = 1,2,..., j = 1,2,...)$<br>$\sum_i \sum_j f(x_i, y_i) = 1$<br>この時の<br>$f_x(x_i) = \sum_j f(x_i, y_j) = P(X = x_i) (i = 1,2,...) \\ f_y(x_i) = \sum_i f(x_i, y_j) = P(X = y_j) (j = 1,2,...)$<br>を$f_x(x_I) \text{と} f_y(y_j)$をそれぞれ$X \text{と} Y$の周辺確率関数という<p><p>連続型<br>$P(a \leq X \leq b, c \leq Y \leq d) = \int_{a}^{b} \int_{c}^{d} f(x, y) dxdy$<br>を同時確率密度関数という<p>$\int_{-\infty}^{\infty} \int_{-\infty}^{\infty} f(x, y) dxdy = 1$<br>となる<br>周辺確率密度関数は<br>$f_x(x) = \int_{-\infty}^{\infty} f(x,y)dy \\ f_y(y) = \int_{-\infty}^{\infty} f(x,y)dx$<br>となる<p><p>期待値<br>$E(X + Y) = E(X) + E(Y) \\ E(X - Y) = E(X) - E(Y)$<br>となり、独立である場合は<br>$E(XY) = E(X)E(Y)$<br>となる<p>分散<br>$V(X + Y) = V(X) + V(Y) + 2Cov(X,Y) \\ V(X - Y) = V(X) + V(Y) - 2Cov(X,Y)$<br>となり、共分散$Xov(X,Y)$が０、すなわち$X$と$Y$が独立である場合には<br>$V(X + Y) = V(X) + V(Y) \\ V(X - Y) = V(X) +V(Y)$が成り立つ<p>２つの確率変数の共分散<br>$Cov(X, Y) = E[(X - \mu_x)(Y - \mu_y)]$<p>相関係数は<br>$\rho = \frac{Cov(X, Y)}{\sqrt{V(X)V(Y)}}$|||
  |||||
  |チェビシェフの不等式|$P(\vert X-\mu \vert \geq k\sigma ) \leq \frac{1}{k^2}$|確率変数$X$が、平均$\mu$、分散$\sigma^2$の確率分布に従うとき、成り立つ不等式<p>**$k$は任意の値で、どんな確率分布の確率変数$X$でも成り立つ**||
  |||||
  |||||
  |||||
  |||||
## 3. 統計的推定
  |名前|数式または記号|説明|関連|
  |:--|:--|:--|:--|
  |||||
  |||||
  |||||
  |||||
  |フィッシャーの3原則||・反復<br>それぞれの処理に対して2回以上の繰り返し実験（評価）を行う<br>反復実験を行って偶然誤差のがらつきが分かれば真の平均のとりうる<br>範囲の測定<br><img src="image-8.png" width="300px"><p>・無作為化<br>実験の順序や場所などが複数ある場合に、比較したい処理群を<br>無作為（ランダム）に割り付けることで、影響の偏りを小さくする。<br>系統誤差を偶然誤差に取り込むことができる<br><img src="image-9.png" width="300px"><p>・局所管理<br>実験を行う時間や場所をブロックごとに区切って、<br>そのブロック内でのバックグラウンドができるだけ均一に<br>なるように管理する系統誤差を小さくする<br><img src="image-10.png" width="300px">||
  |乱塊法||**反復**と**無作為**化に加えて**局所管理**も盛り込んだ実験デザイン<br>基本は局所管理に基づいたブロック内での1セットで<br>実験集めて無作為化を行う<br><img src="image-11.png" width="300px">||
  |中心極限定理||ある母集団から$n$個の標本をとったとき、$n$を大きくすれば<br>標本の平均値は母平均$\mu$、$\frac{\sigma^2}{n}$（母分散を標本で割った数）<br>の正規分布に従う||
  |大数の法則||ある集団から$n$個の標本をとったとき、$n$を大きくすれば<br>標本の平均値は$\bar{X_n}$は、母平均$\mu$に近づいていく||
  |記述統計学と推測統計学||記述統計学：データを整理し、表やグラフで表す<p><p>推測統計学：母集団の標本を使って、母集団の情報を推測する||
  |点推定|$\bar{x} = \frac{1}{n} \sum_{i=1}^{n} x_i $|平均値などを１つの値で推定すること<p>$\hat{\mu}$を推定値という||
  |一致性||推定量を元に母平均や母分散を推測するときに、大数の法則によって<br>サンプルサイズ$n$が大きくなると標本平均が母平均に近づくという性質||
  |不偏性||推定量が母集団パラメータの真の値を平均的に正しく推定する性質||
  |不偏推定量||標本から計算された推定量の期待値が、母集団の真の値と等しくなるような推定量||
  |標本分散|$S^2 = \frac{1}{n} \sum_{i=1}^{n} (x_i - \bar{x})^2$|標本から得られた平均$\bar{x}$からサンプルサイズ$n$として求められる<p>ただし、標本分散は一致推定量ではあるものの不偏推定量でないため<br>$n$が大きくないと標本分散の期待値は母分散に一致せず、母分散よりも<br>小さくなる||
  |不偏分散|$S^2 = \frac{1}{n-1} \sum_{i=1}^{n} (x_i - \bar{x})^2$|標本分散にかわり、標本分散の期待値が母分散に一致するように<br>標本分散の算出式に$\frac{n}{(n-1)}$をかけたものが不偏分散の算出式となります。<br>したがって、不偏分散は一致性と不偏性をもつ推定量です。||
  |標準偏差|$S = \sqrt{\frac{1}{n-1} \sum_{i=1}^{n} (x_i - \bar{x})^2}$|分散の正の平方根で定義される||
  |標準誤差|$SE = \frac{s}{\sqrt{n}} \\ = \frac{\sqrt{\frac{1}{n-1} \sum_{i=1}^{n} (x_i - \bar{x})^2}}{\sqrt{n}}$|標準誤差（SE：standard error）は推定量の標準偏差<p>推定量のバラつきそのものを表す<p>一般的に標本平均の標準偏差を意味する<p>中心極限定理の性質から$n$が大きくなるにつれて<br>正規分布に近づく<p>標本平均の値が母平均に対してどの程度ばらついているかを表す||
  |標準正規分布(z分布)|標準化($\frac{\bar{x} - \mu}{\sqrt{\frac{\sigma^2}{n}}}$)|$\bar{x}$は標本平均<p>標準化した値が標準正規分布の信頼区間の範囲にあるか確認する<p>以下、信頼区間95％の例<br><img src="image-14.png" width="300px"><p>母分散既知の時の母平均の信頼区間を求めるときに使用される||
  |信頼区間の意味||母集団から標本を取ってきて、その平均から95%信頼区間を求める、<br>という作業を100回やったときに、95回はその区間の中に母平均が<br>含まれる<p><img src="image-15.png" width="500px"><p>信頼係数(90％、95％、99％など)が大きいほど、信頼区間の幅は広くなる<p>標本平均が同じであると仮定したときにサンプルサイズｎが大きいほど、<br>信頼区間の幅は狭くなる||
  |t分布||||
  |||||
  |||||
## 4. 統計的仮説検定
  |名前|数式または記号|説明|関連|
  |:--|:--|:--|:--|
  |||||
  |||||
  |||||
  |||||
  |Z分布 (標準正規分布)||定義: 母集団の平均$\mu$と標準偏差$\sigma$が既知のとき<br>、正規分布に従う母集団から抽出された標本平均<br>$\bar{x}$を標準化した値$Z = \frac{\bar{x} - \mu}{\sqrt{\frac{\sigma^2}{n}}}$が従う分布<br><br>特徴: 平均0、分散1の正規分布であり、その形状は<br>左右対称な釣鐘型である<br><br>使い分け:母平均の検定: 母分散が既知の場合に、<br>標本平均が特定の母平均と異なるかどうかを検定<br>する際に用いる<br><br>大標本の場合: 母分散が未知であっても、標本サイズ$n$が<br>十分に大きい（一般的に30以上）場合、中心極限定理<br>により標本分散を母分散の代わりに使用してもZ分布で<br>近似できる。|母平均の検定・推定<br>母分散が既知、もしくはサンプルサイズが<br>十分大きいときに適用|
  |t分布||定義: 母分散が未知の正規母集団から抽出された標本平均<br>を標準化した値$t = \frac{\bar{x} - \mu}{s/\sqrt{n}}$が従う分布で<br>ここで、$s$は不偏標本標準偏差である。<br><br>特徴: 自由度df=n−1によって形状が変化します。<br>自由度が小さいほど裾野が厚く（両端が広がり）、<br>Z分布よりも分散が大きくなります。自由度が大<br>きくなるにつれてZ分布に近づきます。<br><br>使い分け:母平均の検定: 母分散が未知の場合に、標本平均が<br>特定の母平均と異なるかどうかを検定する際に用います。<br>小標本の場合: 特に標本サイズが小さい場合に適しています。|母平均の検定・推定<br>母分散が未知|
  |$χ^{2}$分布 (カイ二乗分布)||定義: 互いに独立で、それぞれが標準正規分布$N(0, 1)$に<br>従う確率変数$Z_1, Z_2, \dots, Z_k$の<br>2乗の和$\chi^2 = Z_1^2 + Z_2^2 + \dots + Z_k^2$が従う分布です。<br><br>特徴: 自由度kによって形状が変化し、非対称で右に歪んだ分布で<br>値は常に0以上になります。<br><br>使い分け:母分散の検定・区間推定: 母集団の分散が特定の母分散<br>と異なるかどうかを検定したり、<br>区間推定を行ったりする際に用います。<br><br>適合度の検定: 観測された度数分布が、理論的な分布と一致するか<br>どうかを検定する際に用います。<br><br>独立性の検定: 2つのカテゴリカル変数が独立であるかどうかを<br>検定する際に用います。|母分散<br>カテゴリカルデータの度数の検定・推定<br>母分散の検定・推定<br>適合度の検定、独立性の検定|
  |F分布||定義: 互いに独立で、それぞれ自由度k1,k2の$\chi^2$分布に従う確率変数<br>W_1, W_2があるとき、$\frac{W_1/k_1}{W_2/k_2}$が従う分布です。<br>特徴: 2つの自由度（分子の自由度k1と分母の自由度k2）によって<br>形状が変化し、非対称で右に歪んだ分布です。値は常に0以上になります。<br><br>使い分け:<br>分散の比較: 2つの母集団の分散が等しいかどうかを検定する（等分散性<br>の検定）際に用います。<br>分散分析 (ANOVA): 3つ以上のグループの平均値が互いに異なるかどうか<br>を検定する際に用います。<br>回帰分析: 回帰モデル全体の適合度を評価する際に用います。|分散の比<br>複数の平均の検定・推定<br>2つの母分散の比較<br>分散分析 (ANOVA)|
  |||||
  |||||
  |P値||||
  |||||
  |||||
  |||||
  |||||
## 5. 線形モデル分析
  |名前|数式または記号|説明|関連|
  |:--|:--|:--|:--|
  |単回帰分析|$y = \beta_0 + \beta_1 x$<br>$\beta_0$は切片<br>$\beta_1$は傾き|目的変数$y$について説明変数$x$を使った式<br>**回帰方程式**や**回帰式**ともいう<p>説明変数が1つなので単回帰となる<p>$\beta_0$と$\beta_1$を求めると回帰式がわかる<p>$\beta_0$と$\beta_1$を求めるには最小二乗法を使用する||
  |最小二乗法|$\sum_{i=1}^{n}e_i^2 = \sum_{i=1}^{n}\begin{Bmatrix} y_i - (\hat{\beta_0} + \hat{\beta_1}x_i) \end{Bmatrix}^2$<p><p>$\beta_0$と$\beta_1$の求め方<br>$\beta_0$と$\beta_1$をそれぞれ微分する<br>$\sum_{i=1}^{n}e_i^2 = \sum_{i=1}^{n}\begin{Bmatrix} y_i - (\hat{\beta_0} + \hat{\beta_1}x_i) \end{Bmatrix}^2$<br>から<br>$\hat{\beta_1} = \frac{\sum_{i=1}^{n}(y_i - \bar{y})(x_i - \bar{x})}{\sum_{i=1}^{n}(x_i - \bar{x})^2}$<br>から<br>$\hat{\beta_0} = \bar{y} - \hat{\beta_1}\bar{x}$|$\beta_0$は切片で$\beta_1$は回帰係数<p><p>性質として、<br>$(y - \bar{y}) = \beta_1 (x - \bar{x})$<br>となる||
  |平方和の分解|$\sum(y_i - \bar{y})^2 = \sum(\hat{y_i} - \bar{y})^2 + \sum(y_i - \hat{y_i})^2 \\ \text{は} \\ S_y(=S_r) = S_R + S_e \\ \text{となる}$|$S_y$：応答変数$y$の変動の大きさを表す<p>$S_R$：回帰による平方和<p>$S_e$：残差平方和||
  |決定係数|$R^2 = \frac{S_R}{S_y} \\ \\ (0 \leq R^2 \leq 1)$|寄与率とも呼ばれ、算出された回帰式の当て<br>はまりの良さを示す<p>||
  |重相関係数|$R = \frac{S_{y\hat{y}}}{S_y S_{\hat{y}}}$|実測値$y$と予測値$\hat{y}$との相関係数<p>$R$と表わされ、二乗すると決定係数$R^2$と等しくなる||
  |重回帰分析|$ y = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \text{...} + \beta_n x_n$|$\beta_0$は切片で<p>$\beta_1 x_1 + \beta_2 x_2 + \text{...} + \beta_n x_n$は偏回帰係数||
  |標準化偏回帰係数||説明変数及び目的変数をそれぞれ<br>標準化した値から算出される偏回帰係数。<p><p>各変数の標準化偏回帰係数どうしを同じ<br>単位で比較できる||
  |偏回帰係数の有意性の検定|$t_i = \frac{\hat{\beta_i} - 0}{se(\hat{\beta_i})}$|$se$は標準誤差<p>定数項を含めた各偏回帰係数$\hat{\beta_i}$が0であるかの検定<p>帰無仮説は偏回帰係数＝0として、偏回帰係数$\hat{\beta_i}$を<br>標準誤差で割った値について、自由度（$n - k -1$）<br>のt分布を用いて検定する。||
  |自由度調整済み決定係数|$R_f^2 = 1 - \frac{\frac{\sum_{i=1}^{n} (y_i - \hat{y})^2}{n-k-1}}{\frac{\sum_{i=1}^{n} (y_i - \hat{y})^2}{n-1}}$|重回帰分析で変数の数が増えていくごとに決定係数<br>の値が良くなるという性質を防ぐための方法||
  |||||
  |||||
  |||||
  |||||
  |||||
  |||||
  |||||
  |||||
  |||||
## 6. その他の分析法