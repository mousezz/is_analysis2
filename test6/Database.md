﻿
- ### USERS表（用户表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |USER_ID|NUMBER(8,0)|主键|否| | | 用户ID|
    |NAME|VARCHAR2(50 BYTE)| |否| | | 用户姓名|
    |GITHUB_USERNAME|VARCHAR2(50 BYTE)| |是|空| | GitHUB用户名|
    |PASSWORD|VARCHAR2(512 BYTE)| |是|空| | 加密存储密码，为空表示密码就是学号|
    |DISABLE|VARCHAR2(20 BYTE)| |否| | |是否禁用,值为是表示禁用,其他表示正常.|

- ### TEACHERS表（老师表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |TEACHER_ID|NUMBER(20,0|主键|否| | | 老师的工号|
    |TEACHER_NAME|VARCHAR2(50 BYTE)|||否| | | 老师的姓名|
    |DEPARTMENT|VARCHAR2(400 BYTE)| |否| | | 老师属于的学院|

- ### TEACHERS_COURSES表（老师教授的课程）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |TEACHER_ID|NUMBER(20,0|主键|否| | | 老师的工号|
    |TCOURSES_ID|NUMBER(8,0)|外键|否| | | 课程的编号|
    |TCOURSES_COU|VARCHAR2(50 BYTE)|外键|否| | | 老师教授的课程|
    |ANN|VARCHAR2(400 BYTE)||否| | | 发布公告|
- ### STUDENTS表（学生表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |STUDENT_ID|NUMBER(20,0|主键|否| | | 学生的学号，为空表示还没有建立用户|
    |GRADES_CLASS|VARCHAR2(20 BYTE)|外键|否| | | 班级编号|
    |STU_NAME|NUMBER(8,0)||是| || 学生的姓名|
    |RESULT_SUM|VARCHAR2(400 BYTE)| |是|空| |成绩集合|
    |WEB_SUM|VARCHAR2(400 BYTE)| |是|空| | GitHub网址是否正确，用逗号分开，Y代表正确，N代表不正确。第1位代表总的GitHUB地址是否正确，第2位表示第1次实验的地址，第3位表示第2位实验地址，依此类推。比如：“Y,Y,Y,Y,Y,N”表示第5次实验地址不正确，其他地址正确|

- ### ALL_STUDENTS表（所有学生列表）
    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |STUDENT_ID|VARCHAR2(50 BYTE)|主键|否| | | 学生的用户ID，USERS表的外键，为空表示还没有建立用户|
    |STU_NAME|VARCHAR2(20 BYTE)||是| || 学生的姓名|
    |GRADES_CLASS|VARCHAR2(20 BYTE)|外键|否| | | 班级编号|
    |ALL_SUUDENTS_LIST|VARCHAR2(20 BYTE)||否| | | 所有学生的列表|

- ### GRADES表（年级表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |STUDENT_ID|VARCHAR2(50 BYTE)|主键|否| | | 学生的用户ID，为空表示还没有建立用户|
    |GRADES_CLASS|VARCHAR2(20 BYTE)|外键|否| | | 班级编号|
    |STU_NAME|VARCHAR2(20 BYTE)||是| || 学生的姓名|
    |NUM_GRADES|NUMBER(8,0)||是| ||班级的学生列表|
    |GRADES_CONFIRM|NUMBER(8,0)||是|是||确认学生是否属于这个班级|


- ### COURSE表（所有课程列表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |STUDENT_ID|VARCHAR2(50 BYTE)|主键|否| | | 学生的用户ID，为空表示还没有建立用户|
    |TCOURSES_ID|NUMBER(8,0)|外键|否| | | 课程的编号|
    |STU_NAME|VARCHAR2(20 BYTE)||是| || 学生的姓名|
    |ALL_COURSES|NUMBER(8,0)||是| ||课程列表|
- ###STUDENT_COURSE表（学生课程表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |TCOURSES_ID|NUMBER(8,0)|外键|否| | | 课程的编号|
    |STUDENT_ID|VARCHAR2(50 BYTE)|联合主键1，外键|否| | | 学生的学号，STUDENTS表外键|
    |COURSE_NAME|NUMBER| |是|空| | 课程名字|
    |ALL_COURSE|NUMBER(8,0)|外键|是| || 学生的姓名|
    |TEST_ANN|VARCHAR2(50 BYTE)|外键|否| | | 作业公告|

- ### TESTS表（实验项目表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |TEACHER_ID|VARCHAR2(50 BYTE)|外键|否| | | 老师的工号|
    |TCOURSES_ID|NUMBER(8,0)|外键|否| | | 课程的编号|
    |STUDENT_ID|VARCHAR2(50 BYTE)|外键|否| | | 学生的学号|
    |TEST_ID|NUMBER(6,0)|主键|否| | | 作业编号|
    |TEST_SCORE1|NUMBER| |是|空| | 学生的个人成绩1|
    |TEST_SCORE2|NUMBER| |是|空| | 学生的个人成绩2|
    |TEST_SCORE3|NUMBER| |是|空| | 学生的个人成绩3|

    