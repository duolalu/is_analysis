# 接口：setScore  [返回](../../README.md)
用例： [评定学生成绩](../用例/评定学生成绩.md)

- 功能：
    评定（修改）学生的成绩和评价。
    
- 权限：
    老师。    
    
- API请求地址： 
    接口基本地址/v1/api/setScore

- 请求方式 ：
    POST

- 请求实例：

        {
            "course_id": "33"
            "student_id": "201510414204"
            "experiment_scores": [{
                "experiment_title": "test1"
                "experiment_score": 90,
                "experiment_comment": "完成的很好",
                "experiment_update_date": "2019-10-2 11:26:17"
                "ScoreItem_scores": [{
                    "ScoreItem_title": "评分点1",
                    "ScoreItem_score": 95,
                    "ScoreItem_comment": "完成的不错"
                },{
                    "ScoreItem_title": "评分点2",
                    "ScoreItem_score": 100,
                    "ScoreItem_comment": "完成的很好",
                    "ScoreItem_update_date":"2019-10-2 11:26:17"
                }]
            }]
        }    
    
        
- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |course_id|课程编号|
  |student_id|学号|
  |course_score|课程成绩|
  |course_comment|课程评价|
  |course_update_date|课程成绩批改时间|
  |experiment_scores|实验成绩集合|
  |experiment_id|实验编号|
  |experiment_score|某个实验成绩|
  |experiment_comment|某个实验评价|
  |experiment_update_date|某个实验批改时间|
  |ScoreItem_scores|评分点成绩集合|
  |ScoreItem_id|评分点编号|
  |ScoreItem_score|评分点成绩|
  |ScoreItem_comment|评分点评价|  
  |ScoreItem_update_date|评分点批改时间|

