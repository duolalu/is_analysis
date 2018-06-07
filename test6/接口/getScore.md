# 接口：getStudentScore  [返回](../../README.md)
用例： [查看成绩](../用例/查看成绩.md)

- 功能：
   根据学号和课程号返回学生该课程的成绩。
    
- 权限：
    老师
    
- API请求地址： 
    接口基本地址/v1/api/getScore

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
  |student_id|学号|
  
  
- 返回实例：

        { 
            "status": true,
            "info": null,
            "data": {
                "course_name": "IT新技术"
                "student_id": "201510414204"
                "student_name":"杜芙宁"
                "course_score": "95",
                "course_comment": "完成的很好"
                "experiment_scores": [{
                    "experiment_title": "test1"
                    "experiment_score": 100,
                    "experiment_comment": "认真完成",
                    "ScoreItem_scores": [{
                        "ScoreItem_title": "评分点1"
                        "ScoreItem_score": 100,
                        "ScoreItem_comment": "第一点完成的很好",
                     },{
                          ....
                         }]
               {
                  ....
                   }]
        }  
- 返回参数说明：    
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |data|返回主体信息JSON串|
  |course_name|课程名称|
  |student_id|学号|
  |student_name|学生姓名|
  |course_score|学生的课程分数|
  |course_comment|课程评语|
  |experiment_title|实验标题|
  |experiment_score|学生对应的实验分数|
  |experiment_comment|实验评语|
  |ScoreItem_name|实验评分点标题|
  |ScoreItem_score|实验对应评分点分数|
  |ScoreItem_comment|评分点评语|
- 注：第一部分省略号为第一个实验其他评分点的成绩，第二部分省略号为其他实验的成绩


