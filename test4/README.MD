# 实验4：图书管理系统顺序图绘制
|      学号    |    班级        |    姓名      |     照片  |   
|:------------:|:-------------- | ------------:|:--------- | 
| 201510414204 | 软件（本） 15-2|   杜芙宁     |     无    |  
## 图书管理系统的顺序图
## 1. 借书用例
### 1.1 借书用例PlantUML源码
```
@startuml
skinparam sequenceArrowThickness 2
skinparam roundcorner 20
skinparam maxmessagesize 60
skinparam sequenceParticipant underline

actor 读者
actor 图书管理员
participant "系统" as A
participant "读者" as B
participant "书" as C
participant "借书记录" as D

读者->图书管理员 :图书编号
读者->图书管理员 :读者借书号
图书管理员 -> A: 登录
activate A
A->图书管理员:验证账户正确性
图书管理员 -> A: 输入读者借书号
A -> B: 获取读者信息
activate B
A -> B: 检查是否可借
deactivate B
loop
A -> C: 查询库存
activate C
C-> A: 返回库存
A -> C: 修改库存
deactivate C
deactivate B
A -> D: 创建借书记录
activate D
deactivate D
A -> 图书管理员: 借出图书
deactivate A
图书管理员->读者:借书成功
end

@enduml


```
### 1.2 借书用例顺序图
![](借出图书.png  "借出图书" )
### 1.3. 借书用例顺序图说明
参与者有读者和图书管理员，涉及到读者类、书类、借书记录类<br/>
过程：读者提供所借图书的编号和借书证号，图书管理员正确登录系统后输入读者账号检查读者限额，如果可借则修改库存
并创建借书记录
## 2. 还书用例
### 2.1 还书用例PlantUML源码
```
@startuml
skinparam sequenceArrowThickness 2
skinparam roundcorner 20
skinparam maxmessagesize 60
skinparam sequenceParticipant underline

actor 读者
actor 图书管理员
participant "系统" as A
participant "读者" as B
participant "书" as C
participant "借书记录" as D
participant "逾期记录" as E

读者->图书管理员 :图书
读者->图书管理员 :读者账号
图书管理员 -> A: 登录
activate A
A->图书管理员:验证账户正确性
图书管理员 -> A: 输入读者借书号
A -> B: 获取读者信息
activate B

deactivate B
A -> C: 修改库存
activate C
deactivate C
deactivate B
A -> D: 记录归还信息
activate D
deactivate D
opt 逾期
图书管理员 -> E:登记逾期记录
activate E
deactivate E
end
deactivate A
A->图书管理员:还书成功
@enduml
```
### 2.2 还书用例顺序图
![](还回图书.png  "归还图书" )
### 2.3. 还书用例顺序图说明
参与者有读者和图书管理员，涉及到读者类、书类、借书记录类、逾期记录类<br/>
过程：读者提供所借图书的编号和借书证号，图书管理员正确登录系统后输入读者账号读取读者信息，修改库存，查看借书记录，如果逾期则创建逾期记录
并创建借书记录
## 3. 查询图书用例
### 3.1 查询图书用例PlantUML源码
```
@startuml
skinparam sequenceArrowThickness 2
skinparam roundcorner 20
skinparam maxmessagesize 60
skinparam sequenceParticipant underline
actor 图书管理员
participant "系统" as A
participant "书" as C
图书管理员 -> A: 登录
activate A
A->图书管理员:验证账户正确性
图书管理员 -> A: 输入图书编号
A -> C: 查询图书信息
activate C
C-> A: 返回查询信息
deactivate C
A -> 图书管理员: 查询成功
deactivate A

@enduml


```
### 3.2 查询图书用例顺序图
![](查询图书.png  "查询图书" )
### 3.3. 查询图书用例顺序图说明
参与者有图书管理员，涉及到书类<br/>
过程：图书管理员正确登录系统后输入图书编号，如果有该图书则返回图书信息
## 4. 预定图书用例
### 4.1 预定图书用例PlantUML源码
```
@startuml
skinparam sequenceArrowThickness 2
skinparam roundcorner 20
skinparam maxmessagesize 60
skinparam sequenceParticipant underline

actor 读者
participant "图书管理系统" as A
participant "读者" as B
participant "书" as C
participant "预订记录" as D

读者 -> A: 登录
activate A
A->读者:验证账户正确性
读者 -> A: 输入借书编号
A -> B: 获取读者信息
activate B
A -> B: 检查是否可预定
deactivate B
A -> C: 查询库存
activate C
A -> C: 修改库存
deactivate C
A -> D: 记录读者信息
activate D
deactivate D
A -> 读者: 预定成功
deactivate A
@enduml

```
### 4.2 预定图书用例顺序图
![](预定图书.png  "预定图书" )
### 4.3. 预定图书用例顺序图说明
参与者有读者，涉及到读者类、书类、预定记录类<br/>
过程：读者输入读者账号后检查读者限额，如果可预定则，创建预定记录。
## 5. 添加读者用例
### 5.1 添加读者用例PlantUML源码
```
@startuml
skinparam sequenceArrowThickness 2
skinparam roundcorner 20
skinparam maxmessagesize 60
skinparam sequenceParticipant underline

actor 读者
actor 图书管理员
participant "系统" as A
participant "读者" as B
读者->图书管理员 :读者信息
图书管理员 -> A: 登录
activate A
A->图书管理员:验证账户正确性
图书管理员 -> A: 输入读者信息
A -> B: 是否有该读者
activate B
loop
A -> B: 添加读者信息
deactivate B
A -> 图书管理员: 添加成功
deactivate A
end
@enduml

```
### 5.2 添加读者用例顺序图
![](添加读者.png  "添加读者" )
### 5.3. 添加读者用例顺序图说明
参与者有读者和图书管理员，涉及到读者类<br/>
过程：读者提供读者信，图书管理员正确登录系统后输入读者信息检查是否有该读者，如果没有则添加读者信息。
## 6. 取消预定用例
### 6.1 取消预定用例PlantUML源码
```
@startuml
skinparam sequenceArrowThickness 2
skinparam roundcorner 20
skinparam maxmessagesize 60
skinparam sequenceParticipant underline

actor 读者
participant "图书管理系统" as A
participant "读者" as B
participant "书" as C
participant "预订记录" as D

读者 -> A: 登录
activate A
A->读者:验证账户正确性
读者 -> A: 输入借书编号
A -> B: 获取读者信息
activate B
A -> B: 检查是否已预定
deactivate B
A -> C: 修改库存
activate C
deactivate C
A -> D: 删除读者预订信息
activate D
deactivate D
A -> 读者: 取消成功
deactivate A
@enduml

```
### 6.2 取消预定用例顺序图
![](取消预订.png  "取消预定" )
### 6.3. 取消预定用例顺序图说明
参与者有读者，涉及到读者类、书类、预定记录类<br/>
过程：读者提供读者信，图书管理员正确登录系统后输入读者信息检查是否有该读者，如果没有则添加读者信息。
