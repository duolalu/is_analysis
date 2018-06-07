# 接口：getCourseInfo  [返回](../../README.md)
用例： [显示课程信息](../用例/显示课程信息.md)

- 功能：
    查看所选修或任教的课程的信息并显示。
    
- 权限：

    
- API请求地址： 
    接口基本地址/v1/api/getCourseInfo

- 请求方式 ：
    GET
    
- 请求实例：

        {
            "student_id": "201510511129",
            "term": "2015-2016学年第1学期"
        }
        
- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |user_id|用户id|
  |term|学期|
  
- 返回实例：

        {         
            "status": true,
            "info": null,
            "data": {[
                "course_id": "22"
                "course_name": "软件分析与设计"
                "course_teacher": "任课老师"
                "course_term": "2017-2018学年第2学期"
                "course_major": "软件工程"
                "course_class": "2015-1，2015-2"
            },{
            ...
            } ]         
        }
 
- 返回参数说明：    
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |data|返回主体信息JSON串|
  |course_id|课程编号|
  |course_name|课程名称|  
  |course_teacher|任课老师|
  |course_term|开课学期|
  |course_major|开课专业|
  |course_class|开课班级|
