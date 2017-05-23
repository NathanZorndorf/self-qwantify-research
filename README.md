# Visualization of Self reported data on activity, emotions, and desire
---

These visualizations were made using data acquired through the qwantify app (qwantify.org), which is an app that uses experience sampling to acquire data about activities that you're engaging in and emotions your feeling, designed as part of a research experiment through Northeastern Univesity. I began using the app 1/12/2017, and I have about 150 data points. 
<br><br>
In order to understand trends, I've visualized the data in a couple of ways. There are many possible ways to slice the data up and plot it, and these are just a few examples. There were some interesting trends that cropped up when I visualized the data, which I'll talk about. 
<br>
It would be very interesting to see how my data looks compared to data from other people! 
<br><br>

# Frequency Distributions
---
1. Frequency Distributions of all Continuous Variables (Histogram)
2. Most Common for all Categorical Variables  (Bar Chart - Count)


```python
df = pd.read_csv('./data/qwantify.csv')
```


```python
df.head()
```


<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>startTime_ISO8601</th>
      <th>startTime_secondsSinceMidnight1Jan1970UTC</th>
      <th>estimatedSecondsSinceAlert</th>
      <th>wantingAnything</th>
      <th>whatWanting</th>
      <th>wantingIntensity</th>
      <th>wantedToFeel_control</th>
      <th>wantedToFeel_lessStress</th>
      <th>wantedToFeel_goodAboutMe</th>
      <th>wantedToFeel_connected</th>
      <th>wantedToFeel_comfort</th>
      <th>wantedToFeel_novelty</th>
      <th>wantedToFeel_calm</th>
      <th>wantedToFeel_health</th>
      <th>wantedToFeel_energy</th>
      <th>wantedToFeel_goodPerson</th>
      <th>wantedToFeel_competent</th>
      <th>wantedToFeel_acknowledged</th>
      <th>wantedToFeel_helpful</th>
      <th>wantedToFeel_other</th>
      <th>wantedToFeel_specifiedOther</th>
      <th>wantedToFeel_nothingInParticular</th>
      <th>doing</th>
      <th>doing_specifiedOther</th>
      <th>withOthers</th>
      <th>feelingBadToGood</th>
      <th>energy</th>
      <th>physically_good</th>
      <th>physically_energized</th>
      <th>physically_hungry</th>
      <th>physically_tired</th>
      <th>physically_uncomfortable</th>
      <th>physically_other</th>
      <th>physically_specifiedOther</th>
      <th>physically_noFeeling</th>
      <th>feeling_angry</th>
      <th>feelingIntensity_angry</th>
      <th>feeling_anxious</th>
      <th>feelingIntensity_anxious</th>
      <th>feeling_awe</th>
      <th>feelingIntensity_awe</th>
      <th>feeling_content</th>
      <th>feelingIntensity_content</th>
      <th>feeling_frustrated</th>
      <th>feelingIntensity_frustrated</th>
      <th>feeling_grateful</th>
      <th>feelingIntensity_grateful</th>
      <th>feeling_happy</th>
      <th>feelingIntensity_happy</th>
      <th>feeling_jealous</th>
      <th>feelingIntensity_jealous</th>
      <th>feeling_loving</th>
      <th>feelingIntensity_loving</th>
      <th>feeling_proud</th>
      <th>feelingIntensity_proud</th>
      <th>feeling_restless</th>
      <th>feelingIntensity_restless</th>
      <th>feeling_sad</th>
      <th>feelingIntensity_sad</th>
      <th>feeling_other</th>
      <th>feeling_specifiedOther</th>
      <th>feeling_noEmotion</th>
      <th>thinkingOverAndOver</th>
      <th>comparingToOthers</th>
      <th>lonely</th>
      <th>selfWorth</th>
      <th>appreciating</th>
      <th>stressed</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2017-05-02T20:11:01-07:00</td>
      <td>1493781061</td>
      <td>2351.0</td>
      <td>2</td>
      <td>Work on data project</td>
      <td>0.494</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>talk</td>
      <td>NaN</td>
      <td>2</td>
      <td>0.633</td>
      <td>0.771</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>1</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>0.000</td>
      <td>NaN</td>
      <td>0.0</td>
      <td>0.629</td>
      <td>0.000</td>
      <td>0.000</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2017-05-02T12:41:30-07:00</td>
      <td>1493754090</td>
      <td>2354.0</td>
      <td>2</td>
      <td>Apply to jobs</td>
      <td>0.281</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>chores</td>
      <td>NaN</td>
      <td>0</td>
      <td>0.506</td>
      <td>0.629</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>NaN</td>
      <td>1</td>
      <td>0</td>
      <td>NaN</td>
      <td>1</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>1</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>0.426</td>
      <td>NaN</td>
      <td>0.0</td>
      <td>0.500</td>
      <td>0.000</td>
      <td>0.104</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2017-05-02T08:34:34-07:00</td>
      <td>1493739274</td>
      <td>7.0</td>
      <td>2</td>
      <td>Paint the stairs</td>
      <td>0.283</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>other</td>
      <td>Meditating</td>
      <td>0</td>
      <td>0.500</td>
      <td>0.502</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>1</td>
      <td>0.175</td>
      <td>NaN</td>
      <td>0.0</td>
      <td>0.363</td>
      <td>0.000</td>
      <td>0.289</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2017-05-01T21:34:24-07:00</td>
      <td>1493699664</td>
      <td>4591.0</td>
      <td>0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>other</td>
      <td>Dancing</td>
      <td>2</td>
      <td>0.633</td>
      <td>0.500</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>1</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>0.000</td>
      <td>NaN</td>
      <td>0.0</td>
      <td>0.514</td>
      <td>0.791</td>
      <td>0.000</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2017-05-01T15:49:41-07:00</td>
      <td>1493678981</td>
      <td>8616.0</td>
      <td>0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>other</td>
      <td>Looking for a job</td>
      <td>0</td>
      <td>0.500</td>
      <td>0.500</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>NaN</td>
      <td>1</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>0</td>
      <td>NaN</td>
      <td>1</td>
      <td>0.000</td>
      <td>NaN</td>
      <td>0.0</td>
      <td>0.502</td>
      <td>0.000</td>
      <td>0.143</td>
    </tr>
  </tbody>
</table>
</div>




## Frequency Distributions
---

### 1. Frequency Distributions of all Continuous Variables (Histogram)

Frequency distributions allow us to get a quick overview of the data, so we can see the distribution of our data, and check whether the data is skewed or abnormally distributed, or if there missing values or outliers.

```python
bins = 20
plt.figure(figsize=(17,11))

sns.set(font_scale=1.4, style='ticks')
for i in range(8):
    plt.subplot(2, 4, i+1)
    sns.distplot(a=df[continuous_cols[i]].dropna(axis=0).values, bins=bins, norm_hist=True, kde=True, color='blue', hist_kws={'alpha':0.6}, kde_kws={'color':'red', 'linewidth':1.5, 'alpha':0.6})
    plt.title('Histogram of {}'.format(continuous_cols[i]))
    
plt.savefig('./images/Histogram of Continuous Variables')
```


![png](/readme-images/output_11_0.png)

Using a histogram with bars gives us a very granular view of the data, and we can see that in the feelingBadToGood, there's very few points in the bin directly to the right of the midpoint (0.5), which I think is just due to a lack of data. But the negeative side of the feelingBadToGood distribution tapers off nicely, and there are many values in between 0 and 0.5, whereas on the positive side, there are very few values between 0.5 and 1, and they cluster around 0.6. Does this suggest that I'm generally a more somber person? Possibly! Or that I need more data (well, we always need more data :p)


```python
bins = 20
plt.figure(figsize=(17,11))

sns.set(font_scale=1.45, style='ticks')

for i in range(8):
    plt.subplot(2, 4, i+1)
    if i != 5:
        sns.distplot(a=df[continuous_cols[i]].dropna(axis=0).values, hist=False, bins=bins, norm_hist=False, kde=True, color='b', \
                 hist_kws={'alpha':0.6}, \
                 kde_kws={'color':'blue', 'linewidth':1.5, 'alpha':0.6, 'shade':True})
    else:
        sns.distplot(a=df[continuous_cols[i]].dropna(axis=0).values, bins=bins, norm_hist=False, kde=False, color='b', \
                 hist_kws={'color':'blue','alpha':0.6}, \
                 kde_kws={'color':'blue', 'linewidth':1.5, 'alpha':0.4})
    plt.title('Histogram of {}'.format(continuous_cols[i]))
    
plt.savefig('./images/KDE (Histograms) of Continuous Variables')
    
    
```


![png](/readme-images/output_12_0.png)

Using the KDE plots allows us to see the general shape of each distribution more easily than the previous chart. Here we can see that the thinkingOverandOver has some outliers, and it might be interesting the explore the context of those oultiers. selfWorth looks skewed positively, and the lonely histogram simple doesn't have enough data points, which is why it's not a smooth KDE plot. 


## Time Series
---

### 1. Hourly Averages for all Continuous Variables 


```python
df['startTime_ISO8601'] = pd.to_datetime(df['startTime_ISO8601'].apply(lambda x: x[:-6]), format='%Y-%m-%dT%H:%M:%S')

df['hour'] = df['startTime_ISO8601'].dt.hour
```


```python
sns.set(font_scale=1.4, style='ticks')

plt.figure(figsize=(8,6))
plt.hist(x=df['hour']);
plt.title('Histogram of Responses by Hour')
plt.savefig('./images/Histogram of Responses by Hour')
```


![png](/readme-images/output_18_0.png)



```python
font = {'size' : 25}

plt.rc('font', **font)
```


```python
sns.set(font_scale=1.4, style='ticks')

plt.figure(figsize=(16,35))

for i in range(len(continuous_cols)):
    
    plt.subplot(len(continuous_cols), 1, i+1)
    
    grouped = df.iloc[df[continuous_cols[i]].dropna(axis=0).index].groupby(by='hour')[continuous_cols[i]].mean()
    plt.plot(grouped.index.values, grouped.values, color='blue')
    
    plt.fill_between(x=grouped.index.values, y1=grouped.values, y2=np.min(grouped.values), facecolor='blue', alpha=0.1)
    
#     count = df.iloc[df[continuous_cols[i]].dropna(axis=0).index].groupby(by='hour')[continuous_cols[i]].count()
#     plt.plot(count.index.values, count.values)
    
    plt.xlim((8,22))
    
    plt.title('{} by Hour'.format(continuous_cols[i]))

plt.tight_layout()

plt.savefig('./images/Continuous Variables By Hour')
```


![png](/readme-images/output_20_0.png)

The time series plots exchibit some interesting trends. Loneliness generally peaks at 5 each day - just when I would have been leaving work for the day, which makes sense as I'm usually taking BART at that time, surrounded by people I don't know (which is generally when I feel the loneliest). SelfWorth peaks at around 3 PM, possibly because I'm hitting my stride at work? Mornings, my favorite time of day, are the least stressed - I still wonder what about mornings is it that causes me to be more relaxed than average? Exploring the morning activities to get some context would be an interesting next step.


### 2. Daily Averages for All Continuous Variables 


```python
df['dayofweek'] = df['startTime_ISO8601'].dt.dayofweek

labels = ['Mon','Tue','Wed','Thur','Fri','Sat','Sun']

plt.figure(figsize=(16,35))

sns.set(font_scale=1.4, style='ticks')

for i in range(len(continuous_cols)):
    
    plt.subplot(len(continuous_cols), 1, i+1)
    
    grouped = df.iloc[df[continuous_cols[i]].dropna(axis=0).index].groupby(by='dayofweek')[continuous_cols[i]].mean()
    plt.plot(grouped.index.values, grouped.values, color='blue')

    plt.fill_between(x=grouped.index.values, y1=grouped.values, y2=np.min(grouped.values), facecolor='blue', alpha=0.1)
    
    plt.xticks(grouped.index.values, labels, rotation=45)
    
    plt.title('{} by Day of Week'.format(continuous_cols[i]))
    
plt.tight_layout()

plt.savefig('./images/Continuous Variables By Day of Week')
```


![png](/readme-images/output_22_0.png)

In the daily averages, we can see peaks for selfWorth and AppreciatingTheMoment on saturdays, which is interesting. The data science Bootcamp was a stressful time period, and this data reflects that time, so it could be that weekdays had me very stressed and comparing myself to classmates might have negatively affected my self-worth. On saturdays I wouldn't have compared myself or felt as much pressure. 


### 3. Frequencies of Categorical Variables as Stacked Line Chart

Create "No Option Selected" column because some rows have no "wanted to feel" option selected.


```python
df['wantedToFeel_noOptionSelected'] = df[wanted_to_feel_cols].any(axis=1).apply(lambda x: 1 if x is True else 0)
```


```python
grouped = df[['hour'] + wanted_to_feel_cols + ['wantedToFeel_noOptionSelected']].groupby(by='hour').sum()

summed = grouped.sum(axis=1)

# Drop any columns that are 0 
grouped = grouped.loc[:, (grouped != 0).any(axis=0)]

# Sum columns 
grouped = grouped.iloc[:,:].div(summed, axis=0)

grouped = grouped.iloc[1:,:]

grouped_summed = grouped

for i in range(1,len(grouped_summed.columns)):
    grouped_summed.iloc[:, i] += grouped_summed.iloc[:, i-1]
```

Plot


```python
fig, ax = plt.subplots(figsize=(16,12))

color = iter(plt.cm.gist_rainbow(np.linspace(0,1,len(grouped_summed.columns))))

for i in range(len(grouped_summed.columns)):
    
    c = next(color)
    
    label = grouped_summed.iloc[:, i].name

    ls = '-'
    lw = 0.15
    ax.plot(grouped_summed.index.values, grouped_summed.iloc[:, i].values, color=c, label=label, ls=ls, lw=0.1, alpha=0.6, visible=True)
    ax.plot(grouped_summed.index.values, grouped_summed.iloc[:, i].values, color='black', ls=ls, lw=lw, alpha=0.8, visible=True)

    
    alpha = 0.38
    if i == 0:
        ax.fill_between(x=grouped_summed.index.values, y1=grouped_summed.iloc[:, i].values, y2=0, facecolor=c, alpha=alpha)    
    elif i==len(grouped_summed.columns)-1:
        ax.fill_between(x=grouped_summed.index.values, y1=grouped_summed.iloc[:, i].values, y2=grouped_summed.iloc[:, i-1].values, facecolor='white', alpha=alpha)
    else:
        ax.fill_between(x=grouped_summed.index.values, y1=grouped_summed.iloc[:, i].values, y2=grouped_summed.iloc[:, i-1].values, facecolor=c, alpha=alpha)
    
ax.set_xlim((8,22))

ax.set_ylabel('Relative Frequency')
ax.set_xlabel('Time of Day')    
ax.set_title('Relative Frequency of Want To Feel Selections by Time of Day')

# Shrink current axis by 20%
box = ax.get_position()
ax.set_position([box.x0, box.y0, box.width * 0.8, box.height])

# Put a legend to the right of the current axis
legend = ax.legend(loc='center left', bbox_to_anchor=(1, 0.5))

frame = legend.get_frame()

# Set the fontsize
for label in legend.get_texts():
    label.set_fontsize('large')

for i,legobj in enumerate(legend.legendHandles):
    legobj.set_linewidth(3.0)
    if i == len(grouped_summed.columns)-1:
        legobj.set_color('white')

fig.tight_layout()

plt.savefig('./images/want_to_feel_relative_frequency_by_hour', bbox_extra_artists=(legend,), bbox_inches='tight')

```


![png](/readme-images/output_28_0.png)

This chart is like the hourly time series plots, but allows us to compare the frequency my desires to one another on an hourly basis. My desire to feel compotent exceeds any other desire at 3 PM, also the same time I felt the most self-worth. And at 5, I want to feel the most connected with others, which matches the plot showing how loneliness peaked at 5 PM.


### Relative Frequency of Want to Feel by Day of Week


```python
grouped = df[['dayofweek'] + wanted_to_feel_cols + ['wantedToFeel_noOptionSelected']].groupby(by='dayofweek').sum()

summed = grouped.sum(axis=1)

grouped = grouped.loc[:, (grouped != 0).any(axis=0)]

grouped = grouped.iloc[:,:].div(summed, axis=0)

grouped_summed = grouped

for i in range(1,len(grouped_summed.columns)):
    grouped_summed.iloc[:, i] += grouped_summed.iloc[:, i-1]
```


```python
fig, ax = plt.subplots(figsize=(16,12))

color = iter(plt.cm.gist_rainbow(np.linspace(0,1,len(grouped_summed.columns))))

labels = ['Mon','Tue','Wed','Thur','Fri','Sat','Sun']

for i in range(len(grouped_summed.columns)):
    
    c = next(color)
    
    label = grouped_summed.iloc[:, i].name

    ls = '-'
    lw = 0.15
    ax.plot(grouped_summed.index.values, grouped_summed.iloc[:, i].values, color=c, label=label, ls=ls, lw=0.1, alpha=0.6, visible=True)
    ax.plot(grouped_summed.index.values, grouped_summed.iloc[:, i].values, color='black', ls=ls, lw=lw, alpha=0.8, visible=True)

    
    alpha = 0.38
    if i == 0:
        ax.fill_between(x=grouped_summed.index.values, y1=grouped_summed.iloc[:, i].values, y2=0, facecolor=c, alpha=alpha)    
    elif i==len(grouped_summed.columns)-1:
        ax.fill_between(x=grouped_summed.index.values, y1=grouped_summed.iloc[:, i].values, y2=grouped_summed.iloc[:, i-1].values, facecolor='white', alpha=alpha)
    else:
        ax.fill_between(x=grouped_summed.index.values, y1=grouped_summed.iloc[:, i].values, y2=grouped_summed.iloc[:, i-1].values, facecolor=c, alpha=alpha)
    
ax.set_xlim((0,1))
ax.set_ylabel('Relative Frequency')
ax.set_xlabel('Day of Week')    
ax.set_title('Relative Frequency of Want To Feel Selections by Day of Week')

plt.xticks(grouped_summed.index.values, labels, rotation=45)

# Shrink current axis by 20%
box = ax.get_position()
ax.set_position([box.x0, box.y0, box.width * 0.8, box.height])

# Put a legend to the right of the current axis
legend = ax.legend(loc='center left', bbox_to_anchor=(1, 0.5))

frame = legend.get_frame()

# Set the fontsize
for label in legend.get_texts():
    label.set_fontsize('large')

for i,legobj in enumerate(legend.legendHandles):
    legobj.set_linewidth(3.0)
    if i == len(grouped_summed.columns)-1:
        legobj.set_color('white')

fig.tight_layout()

plt.savefig('./images/want_to_feel_relative_frequency_by_day', bbox_extra_artists=(legend,), bbox_inches='tight')
```


![png](/readme-images/output_31_0.png)

Here we can see that my desire to feel conencted increases as the week goes on, whereas my desire for being in control of my situation decreases as the weekend approaches. 


## Aggregations 
---

### 1. Count of Categorical Variables


```python
def get_feeling_type(row):
    for c in feeling_type_cols:
        if row[c] == 1:
            return c
```


```python
df['feelingType'] = df.apply(get_feeling_type, axis=1)
```


```python
plt.figure(figsize=(12,6))

sns.set(font_scale=1.4, style='ticks')

g = sns.countplot(df[~df['feelingType'].isnull()].loc[:,'feelingType'])

plt.xticks(rotation=55, horizontalalignment='right')
plt.title('Count of Feeling Types')

plt.savefig('./images/Count of Feeling Types')
```


![png](/readme-images/output_36_0.png)


## Correlations
---

### Find Correlation Between Continuous Variables


```python
plt.figure(figsize=(17,40))

sns.set(font_scale=1.4)

with sns.axes_style( style="ticks"):
    g = sns.pairplot(df[continuous_cols].dropna(axis=0), kind="reg", diag_kind='kde', size=3, \
                     diag_kws=dict(shade=True), \
                    plot_kws={'line_kws':{'color':'red'}})
    
    for i, j in zip(*np.triu_indices_from(g.axes, 1)):
        g.axes[i,j].set_visible(False)

plt.savefig('./images/Relationships between Continuous Variables')
```


    <matplotlib.figure.Figure at 0x116138690>



![png](/readme-images/output_39_1.png)

This pairplot allows us to immediately spot correlations between the continuous variables of the data set. Energy and self worth are positively correlated, whereas energy and stress are negatively correlated - just a few relationships that stand out.


### Scatter plot of the average Intensity of Want vs. Energy for each activity


```python
# Don't use rows that have 0 wanting, aka drop rows with null values in 'wantingIntensity'
dfc = df[pd.notnull(df['wantingIntensity'])]

# Need to make 2 dataframes, one that is the average intensity of want and average energy grouped by activity
df2 = pd.concat(objs=[dfc['wantingIntensity'], dfc['energy'],dfc['doing']], axis=1)

grouped_means = df2.groupby(by='doing').mean()

# Other dataframe is the frequency count of each activity 
grouped_count = pd.concat(objs=[dfc['doing'],pd.get_dummies(data=dfc['doing'])], axis=1, names=['count']).groupby(by='doing').count().iloc[:,0]

grouped_count.name = 'count'

df2 = pd.concat(objs=[grouped_means, grouped_count], axis=1)

df2['count'] = df2['count'] / df2['count'].sum()
```

Plot


```python
s = [x*20000 for x in df2['count'].values]

c = plt.cm.gist_rainbow(np.linspace(0,1,len(df2.index)))

fig, ax = plt.subplots(figsize=(12,8))

for i in range(len(df2.index.values.tolist())):

    x = df2['wantingIntensity'].values[i]
    y = df2['energy'].values[i]
    ind = df2.index.values[i]
    
    ax.scatter(x, y, s=s[i], c=c[i], alpha=0.6, label=ind, edgecolors='black')
    
    ax.annotate(s=ind, xy=(x,y), )

plt.xlabel('Wanting Intensity')
plt.ylabel('Energy')
plt.title('Wanting Intensity vs. Energy per Activity, with frequency of activity')

mid_y = (plt.ylim()[0] + plt.ylim()[1]) / 2
mid_x = (plt.xlim()[0] + plt.xlim()[1]) / 2

ax.set_yticks([mid_y], minor=True)
ax.set_xticks([mid_x], minor=True)
ax.yaxis.grid(True, which='minor')
ax.xaxis.grid(True, which='minor')


plt.grid(False)

fig.tight_layout()

plt.savefig('./images/intensity_of_want_vs_energy_for_each_activity', bbox_extra_artists=(legend,), bbox_inches='tight')
```


![png](/readme-images/output_43_0.png)


This plot allows us to see the average wanting intensity vs. energy or each general activity that I engage in. the size of the bubble represents the frequency for which I engage in that activity - here I spend the most time working, and the least time exercising. When I'm traveling, I generally have a high wanting intensity and high energy, which makes sense - when I'm traveling I'm eagerly anticipating my next activity. Leisure, not surprisingly has a high wanting intensity, but low energy - I'm relaxing! 

<br>
I'm very curious how this plot would look for other people. I think that personalities would pop out more apparently with this chart. 
