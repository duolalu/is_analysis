# 接口：getStudents  [返回](../../README.md)
用例： [显示学生列表](../用例/显示学生列表.md)

- 功能：
   根据课程编号显示学生列表。
    
- 权限：
    老师。    
    
- API请求地址： 
    接口基本地址/v1/api/getStudents

- 请求方式：
    GET

- 请求实例：

        {
            "course_id": "11"
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
                "course_num":"120"
                "students": [{
                    "student_id": "201510414204",
                    "major": "软件工程",
                    "class": 2,
                    "web_sum": "y",
                    "github_username":"duolalu"
                    "name":"杜芙宁"
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
  |course_num|本课程的总人数|
  |students|返回本课程学生集合，若空则返回[]|
  |student_id|学生学号|
  |major|专业|  
  |class|班级|
  |web_sum|学生GitHub地址是否正确，1正确，0错误|
  |name|学生姓名|
  |github_username|GitHub用户名|
