# Robo Stock Advisor
This is an algorithmic portfolio manager/advisor that—given a file with a list of stock tickers—will create a portfolio designed for risk-averse investors (i.e., it will optimize for the lowest possible returns).

This was a project for the Computing and Financial Management program at the University of Waterloo. All groups' programs were tested on live stock data and compared against each other; this group came in third place in the program.

The process to create the portfolio is as follows:
1. Stock data is filtered (any stocks that are delisted or don't meet certain requirements are removed).
2. Candidate stocks are selected using statistical measures such as standard deviation, expected return, beta value, and correlation. Stock candidates are selected to ensure a low and stable expected return. Several candidate portfolios will be created using these candidate stocks, and later we will choose one of these portfolios as the final portfolio.
3. Once we have the candidate portfolios, the stocks' weightings in each portfolio are optimized by creating about 2,000 random weighting variations per portfolio candidate.
4. Finally, to choose which portfolio candidate we select as the final portfolio, we use a geometric approach in which the portfolio closest to the origin on a risk-return plane is picked. In other words, we optimize for both low expected returns and low standard deviation because these are both important in this project.

Below you can see an image of all random portfolios graphed on a risk-return plane. Each colour represents a different portfolio candidate, and the black dot is the optimal portfolio.
![image](https://github.com/Zemelware/robo_stock_advisor/assets/61860124/c62db596-5dca-4f89-91e3-873035ddd352)

The final portfolio will look something like this:
<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Ticker</th>
      <th>Price</th>
      <th>Currency</th>
      <th>Shares</th>
      <th>Value</th>
      <th>Weight</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>RY.TO</td>
      <td>118.959999</td>
      <td>CAD</td>
      <td>1171.745860</td>
      <td>139390.886413</td>
      <td>0.185861</td>
    </tr>
    <tr>
      <th>2</th>
      <td>T.TO</td>
      <td>24.059999</td>
      <td>CAD</td>
      <td>2408.955568</td>
      <td>57959.469683</td>
      <td>0.077286</td>
    </tr>
    <tr>
      <th>3</th>
      <td>TD.TO</td>
      <td>83.349998</td>
      <td>CAD</td>
      <td>1495.364161</td>
      <td>124638.600532</td>
      <td>0.166191</td>
    </tr>
    <tr>
      <th>4</th>
      <td>KO</td>
      <td>80.211615</td>
      <td>USD</td>
      <td>212.504861</td>
      <td>17045.358176</td>
      <td>0.022734</td>
    </tr>
    <tr>
      <th>5</th>
      <td>PEP</td>
      <td>231.952210</td>
      <td>USD</td>
      <td>73.465596</td>
      <td>17040.507405</td>
      <td>0.022727</td>
    </tr>
    <tr>
      <th>6</th>
      <td>CL</td>
      <td>105.876042</td>
      <td>USD</td>
      <td>167.983406</td>
      <td>17785.418206</td>
      <td>0.023720</td>
    </tr>
    <tr>
      <th>7</th>
      <td>PG</td>
      <td>207.314918</td>
      <td>USD</td>
      <td>84.876343</td>
      <td>17596.132203</td>
      <td>0.023468</td>
    </tr>
    <tr>
      <th>8</th>
      <td>BMY</td>
      <td>68.146318</td>
      <td>USD</td>
      <td>250.069619</td>
      <td>17041.323858</td>
      <td>0.022728</td>
    </tr>
    <tr>
      <th>9</th>
      <td>MRK</td>
      <td>139.510970</td>
      <td>USD</td>
      <td>840.021872</td>
      <td>117192.266055</td>
      <td>0.156263</td>
    </tr>
    <tr>
      <th>10</th>
      <td>PM</td>
      <td>129.198626</td>
      <td>USD</td>
      <td>131.895760</td>
      <td>17040.750973</td>
      <td>0.022728</td>
    </tr>
    <tr>
      <th>11</th>
      <td>ABBV</td>
      <td>189.908564</td>
      <td>USD</td>
      <td>95.048040</td>
      <td>18050.436834</td>
      <td>0.024074</td>
    </tr>
    <tr>
      <th>12</th>
      <td>LMT</td>
      <td>619.027713</td>
      <td>USD</td>
      <td>27.528353</td>
      <td>17040.813296</td>
      <td>0.022728</td>
    </tr>
    <tr>
      <th>13</th>
      <td>MO</td>
      <td>56.793167</td>
      <td>USD</td>
      <td>300.190751</td>
      <td>17048.783489</td>
      <td>0.022738</td>
    </tr>
    <tr>
      <th>14</th>
      <td>ABT</td>
      <td>140.880470</td>
      <td>USD</td>
      <td>123.428161</td>
      <td>17388.617273</td>
      <td>0.023191</td>
    </tr>
    <tr>
      <th>15</th>
      <td>UNH</td>
      <td>749.253422</td>
      <td>USD</td>
      <td>22.795996</td>
      <td>17079.977869</td>
      <td>0.022780</td>
    </tr>
    <tr>
      <th>16</th>
      <td>PFE</td>
      <td>41.769750</td>
      <td>USD</td>
      <td>407.962823</td>
      <td>17040.505251</td>
      <td>0.022727</td>
    </tr>
    <tr>
      <th>17</th>
      <td>UNP</td>
      <td>307.151461</td>
      <td>USD</td>
      <td>55.816962</td>
      <td>17144.261311</td>
      <td>0.022866</td>
    </tr>
    <tr>
      <th>18</th>
      <td>UPS</td>
      <td>208.205085</td>
      <td>USD</td>
      <td>85.818505</td>
      <td>17867.849137</td>
      <td>0.023830</td>
    </tr>
    <tr>
      <th>19</th>
      <td>BK</td>
      <td>64.845823</td>
      <td>USD</td>
      <td>264.429332</td>
      <td>17147.137784</td>
      <td>0.022869</td>
    </tr>
    <tr>
      <th>20</th>
      <td>ACN</td>
      <td>457.467795</td>
      <td>USD</td>
      <td>37.249720</td>
      <td>17040.547166</td>
      <td>0.022727</td>
    </tr>
    <tr>
      <th>21</th>
      <td>TXN</td>
      <td>210.341502</td>
      <td>USD</td>
      <td>81.036586</td>
      <td>17045.357171</td>
      <td>0.022734</td>
    </tr>
    <tr>
      <th>22</th>
      <td>BAC</td>
      <td>40.715235</td>
      <td>USD</td>
      <td>424.069763</td>
      <td>17266.099914</td>
      <td>0.023028</td>
    </tr>
  </tbody>
</table>
</div>


If you're interested, more information and explanations can be found in the Jupyter Notebook file.

