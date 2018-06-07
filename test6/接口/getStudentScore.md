# 接口：getStudentScore  [返回](../../README.md)
用例： [查看学生成绩](../用例/查看学生成绩.md)

- 功能：
   根据课程编号返回成绩列表。
    
- 权限：
    老师
    
- API请求地址： 
    接口基本地址/v1/api/getStudentScore

- 请求方式：
    GET

- 请求实例：

        {
            "course_id": "22",
        }
        
- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |course_id|课程编号|
  
  
- 返回实例：

        { 
            "status": true,
            "info": null,
            "data": {
            "course_name": IT新技术"
            "course_num":120
            "students": [{
            "student_id": "201510414204",
            "name":"杜芙宁",
            "course_score": 90,
            "experiment_title": "test1",
            "experiment_score": 95,
            "Scoretem_name":"评分点1"
            "ScoreItem_score": 100,
                },{
                    ...
                }]   
            }    
        }
- 返回参数说明：    
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |data|返回主体信息JSON串|
  |course_name|课程名称|
  |students|学生信息|
  |student_id|学号|
  |name|学生姓名|
  |course_score|学生的课程分数|
  |experiment_title|实验标题|
  |experiment_score|学生对应的实验分数|
  |ScoreItem_name|实验评分点标题|
  |ScoreItem_score|实验对应评分点分数|
- 注：省略号部分为剩下同学的成绩


