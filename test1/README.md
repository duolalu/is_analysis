#流程图1：考试及成绩管理流程
###PlantUML源码如下：
```
@startuml
|教务处|
start
:安排考试;
:考试安排表;
|教师|
:出卷;
split
:A、B试卷;
split again
:打印审批表;
|系主任|
:审批签字;
:打印审批表;
endsplit
|教务处|
:打印试卷;
:试卷;
|学生|
:参加考试;
:答卷;
|教师|
:阅卷出成绩;
split
    :成绩单;
      |教务处|
     if (有不及格?) then (有)
     :安排补考;
     endif
     fork
     :补考安排表;
     detach
     fork again
     endfork
|教师|
split again
    :答卷;
    :装订存档;
    endsplit
:期末流程结束;
@enduml
```
###业务流程图如下：
![](examPro.png '描述')
###流程说明：
考试及成绩管理流程共涉及教务处、教室、系主任、学生四种角色<br>
1、教务处安排考试并排好安排表<br>
2、教师出A/B试卷，打印审批表<br>
3、系主任审批教师的审批表签字，然后打印审批表<br>
4、教务处打印试卷<br>
5、学生参加考试<br>
6、教师阅卷出成绩、答卷装订存档<br>
7、如果有不及格的则教务处安排补考
#流程图2：客户维修服务流程
###PlantUML源码如下：
```
@startuml
|客户|
start
:申请服务;
|业务经理|
if(是新用户吗?)then(是)
:登记客户信息;
else(不是)
endif
:上门勘察;
:制定方案;
|客户|
if(满意吗？)then(否)
stop
else(是)
:签订服务合同;
endif
|业务经理|
fork
:安排工人;
forkagain
:安排材料;
endfork
:填写派工单;
|工人|
:领取材料;
:上门服务;
|客户|
:验收并填写反馈意见
|业务经理|
:交回派工单;
|财务人员|
:结算收款;
stop
@enduml
```
###业务流程图如下：
![](maintenance.png '描述')
###流程说明：
客户维修服务流程涉及到客户、业务经理、工人、财务人员四种角色<br>
1、客户申请服务<br>
2、业务经理确定该客户是否为新客户、如果是则登记客户信息然后上门勘察，不是则直接上门勘察
接着制定方案<br>
3、客户是否满意方案，如果满意则签订服务合同，不满意则终止流程<br>
4、在客户满意的前提下，业务尽力安排工人和材料，填写派工单<br>
5、工人领取材料、上门服务<br>
6、客户验收并填写反馈意见<br>
7、由业务尽力交回派工单并交给财务人员结算收费<br>