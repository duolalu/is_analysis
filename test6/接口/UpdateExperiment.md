# 接口：UpdateExperiment  [返回](../../README.md)
用例：[修改课程作业](../用例/修改课程作业.md)

- 功能：
   修改指定课程的实验信息。
    
- 权限：
    老师。    
    
- API请求地址： 
    接口基本地址/v1/api/UpdateExperiment

- 请求方式 ：
    POST

- 请求实例：

        {
            "course_id": "2020220",
            "experiment_title": "软件系统分析与设计test1",
            "experiment_content": "熟练掌握类图的画法",
            "experiment_last_date": "2018-6-4 11:51:30"
        }    
    
        
- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |course_id|课程编号|
  |experiment_title|实验标题|
  |experiment_content|实验内容|
  |experiment_last_date|实验截至时间|

  
- 返回实例：

        {         
            "status": true,
            "info": null,    

        }
 
- 返回参数说明： 
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|

