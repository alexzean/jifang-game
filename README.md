# jifang-game
机房杀

## 更新日志

2024.1.23 提交至github。具体更新看游戏信息。

2024.1.27 可以增加AI了，但是这个AI就是从所有可选项中随机选一个，不知道有什么用。

2024.1.29 游戏细节优化，修复bug

2024.1.30 增加统计信息显示

2024.1.31 增加功能：卡牌稀有度

2024.4.12 增加卡牌：机惨

2024.4.13 增加功能：禁用卡牌

## 游戏作者
lyr、xza、cyq（姓名拼音缩写）

## 游戏规则
### 游戏流程
1.每回合结束时，将手中的牌弃到6张。

2.角色技能如果没有备注，每回合限一次，牌没有限制。

3.成绩<0时让成绩=0，然后生命-2，生命=0时如果没有特殊技能，角色死亡。

4.每回合开始时，摸2张牌。

5.游戏开始时，角色的生命为20，成绩为100，知识点为0。

### 游戏卡牌
普通（不显示稀有度）卡牌效果：

1.学新知识点：成绩+10，知识点+1

2.做题：成绩加上知识点数量*0.5（向上取整）

3.狂人卷题：生命-1，成绩+知识点数量*1

4.禁止内卷：所有角色本轮无法使用卡牌1、2、3。

5.腐败：生命+1，成绩-7。

6.一起腐败：你选择一名其他角色，你与其生命各+2，你成绩-8，其成绩-10。

7.向AJ举报：你选择一名其他角色，其生命-1，如果其本轮成为过卡牌5、6的目标，改为生命-2。

8.急眼：你选择一名其他角色，其生命-2，你成绩-5，然后如果其本轮成为过卡牌5、6的目标，其成绩-5。

9.翻墙：除了本回合成为卡牌1、2、3的目标的人外，其他所有角色成绩-7，生命-1，然后你有50%概率成绩-3，生命-1。

10.机惨：你选择一名其他角色，其成绩在接下来3回合中每回合-1，并且不能使用卡牌（卡牌正常抽取，可以弃牌）

有概率摸到更高稀有度（依次为：普通；罕见；稀有；传奇；神话），每一级有益效果*1.67（对最终结果向上取整），优先于被动技能。

### 游戏角色
1.lyr：使用卡牌5时生命+1，成绩-2。
  
- 腐败王：你可以视为使用了一张卡牌5，本轮其他所有角色无法使用卡牌1。
- 制裁：你可以自减5点生命，本轮其他所有角色无法使用卡牌4、5、6。
                
2.xza：使用卡牌1时成绩+2，成为卡牌6的目标时成绩减少1/4。
  
- 蓝勾爷：你使用卡牌2、3时，效果结算后*1.6。
- 透明度：你使用卡牌5、6时有10%概率视为使用卡牌2且不视为腐败。
                
3.cyq：使用卡牌5、6时有40%概率成绩-7。
  
- 急眼哥：你使用卡牌8时改为“所有其他角色生命-2，你成绩-7，然后如果有其他角色本轮成为过卡牌5、6的目标，其成绩-5。”
- 出题人：你可以令所有其他角色视为使用卡牌2，以此法使用的卡牌2改为“成绩加上知识点数量*0.1（向上取整 ）”，然后你成绩+5。
                
4.wcy：每局限两次，你的生命每-1，成绩+2，成绩若>300，生命再+2。
  
- 秒题：你使用的卡牌2改为“成绩+知识点数量*0.8“。
- 水谷：你可以令所有角色本轮无法使用卡牌4，已有的禁止内卷效果无效。
                
5.nmk：每轮摸1张卡牌5。
  
- 腐败小助手：你使用卡牌5、6时不视为腐败。
- 你是个废物！：你选择一名角色，令其弃置手中的所有卡牌1、2、3。
                
6.AJ：在你腐败时，其它角色对你使用的卡牌7改为“你自减2点生命”。
  
- 抓腐：你使用卡牌7时。
- 不死之身：每局限两次，若你的生命<=2且不为0，你选择一项：1.生命+2；2.你选择一名其它角色，令其生命-5 ，成绩=0，然后你死亡。
                
### 禁用卡牌

你可以将一个配置文件拖入可执行文件中，配置文件由若干行组成，每一行格式形如 `[name delete=c1[,c2,c3,...]]`。

- `name`表示你要对其使用禁用的玩家名称。

- `c1,c2,c3,...`依次表示你要对此玩家禁用的卡牌名称，你指定的玩家在接下来的所有游戏中都不能使用这些卡牌。
