# Asphalt9win
**Latest changes**  
Added minimal navigation for daily tasks (such as CreditHeist, OpenClassCup, etc.)  

At the moment in this build there is minimal navigation data, the bot rides in simple mode without nav. So the **-map** option applies only to existing nav data. The bot can temporarily reach the legend with a good garage.  
Also, the bot's operating time is limited to **Q2** 2022  
<a href = "https://youtu.be/W1rB03THwyM" target = "_blank">Grand Prix race example</a> (vs manual drive 😓)  
<a href = "https://youtu.be/S8zHejao2aM" target = "_blank">Exclusive Egoista (Naniwa Tour) BEAT 1:18 By 1* Corvette ZR1</a> (hybrid drive at 0:35|25% track)  
See the nav in the «Navigations» folder  

**Command line arguments:**  
| **Argumnent**     | **Short**         | **Description**  |
| ------------- |:-------------:|:-----|
| -task         |-t | Single task name |
|-repeat        |-r | Number of repetitions of a single task |
|-param         |-p | String parameter for a single task | 
|-cars          |-c | Cars preset for a single task like Hunt |
|-map           |-m | Forced navigation setting |
|-minTime       |   | Driving no better than a set time  (Race & Hunt only) |
|-maxTime       |   | Driving no worse than the set time (Race & Hunt only) |
|-file          |-f | Path to the file with multiple task |
|-delay         |-d | Pre-start pause in seconds (default = 0) |
|-windowName    |-n | A9 window name (default «Asphalt 9: Legends») |
|-windowX       |-x | Set the window to the specified X coordinate (default = -7) |
|-windowY       |-y | Set the window to the specified X coordinate (default = 0) |
|-windowWidth   |-w | Set the specified window width (default = 1056) |
|-windowHeight  |-h | Set the specified window height (default = 521) |

**Examples:**  
*BCompilerDebug.exe* -t **MP1** -r **100**  
*BCompilerDebug.exe* -t **MP2** -r **100**  
*BCompilerDebug.exe* -t **Hunt** -r **5** -cars **B4** -map **"The Caribbean: ISLET RACE"**  
*BCompilerDebug.exe* -t **Hunt** -r **1** -cars **C4** -map **hunt1bps** -minTime **60** -maxTime **64**  
*BCompilerDebug.exe* -t **Race** -r **1** -map **"Osaka: NANIWA TOUR"** (*execute from car lobby*)  
*BCompilerDebug.exe* -t **NavStat**  
*BCompilerDebug.exe* -t **ShowStats**  

*BCompilerDebug.exe* -f **EveryDay.txt**  
> *EveryDay.txt*  
```javascript
//daily tasks
DailyEvents 6 Hunt cars:C4
//Hunt 3 cars:C4 map:Buenos_Aires:_CROSSTOWN event:HUNT_ELVA
//MP1Downgrade 10 silver
//MP2 15
MP1 25
```
*BCompilerDebug.exe* -f **EveryHour.txt**  (*run from the windows scheduler*)  
> *EveryHour.txt*  
```javascript
//one hour tasks
DailyEvents 6 Hunt cars:C4
//MP1Downgrade 15 bronze
//MP1 15
//MP2 5
Kill 1
Exit 1
```

For Hunt you need to update the file ..\Source\DailyEvents\HUNT_CAR {LOC_B40,TLR_0.85}.png  
![image](https://user-images.githubusercontent.com/25618671/162742234-eea4a324-7765-46fa-90c2-f4e41799c068.png)

> File name parser rules:  

../Source/../FileName {OPTIONS}.png  
- OPTIONS: (comma separated options)  
  * _TLR_ - Template searching tolerance (ex: **TLR_0.8**). The default tolerance is 0.98  
  * _LOC_ - The location of the image you are looking for (ex: **LOC_BR40** which means bottom right 40% of screen). B - bottom, T - top, L - left, R - right  
  * _AREA_ - Describes the search area in the image, where XY is the upper left corner, WH is the area size (ex: **AREA_X1300Y300W650H155**)  

> *race-stats.txt* example  

![image](https://user-images.githubusercontent.com/25618671/162734720-89aad2ef-20e7-4133-824d-b1a506c45562.png)

___
###### <a href = "https://paypal.me/AzamatGizatullin" target = "_blank">PayPalMe</a>
