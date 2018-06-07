# 接口：getCourses  [返回](../../README.md)
用例： [选择课程](../用例/选择课程.md)

- 功能：
   根据用户ID和course_id显示课程信息。
    
- 权限：
    学生，老师。    
    
- API请求地址： 
    接口基本地址/v1/api/getCourses

- 请求方式：
    GET

- 请求实例：

        {
            "student_id": "201510511129",
            "term": "2015-2016学年第1学期"
        }
        
- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |student_id|学生学号|
  |term|学生所修的学期|

  
- 返回实例：

        { 
            "status": true,
            "info": null,
            "data": {
                    "course_id": "055441",
                    "course_name": "C语言基础",
                    "course_teacher":"任课老师",
                    "course_num":"120",
                    "course_major":"软件工程",
                    "course_class":"开课班级"

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
  |course_num|课程人数|
  |course_major|开课专业|
  |course_class|开课班级|
