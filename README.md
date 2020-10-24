# 一、实验内容
##### (1)初步了解分析系统需求，从学生选课角度了解系统中的实体及其关系，学会定义类中的属性以及方法；
##### (2)掌握面向对象的类设计方法（属性、方法）；
##### (3)掌握类的继承用法，通过构造方法实例化对象；
##### (4)学会使用super()，用于实例化子类；
##### (5)掌握使用Object根类的toString（）方法,应用在相关对象的信息输出中。

# 二、实验要求
学校有“人员”，分为“教师”和“学生”，教师教授“课程”，学生选择“课程”。从简化系统考虑，每名教师仅教授一门课程，每门课程的授课教师也仅有一位，每名学生选仅选一门课程。
对象示例：	人员（编号、姓名、性别……）
教师（编号、姓名、性别、所授课程、……）
学生（编号、姓名、性别、所选课程、……）
课程（编号、课程名称、上课地点、时间、授课教师、……）
##### 1.编写上述实体类以及测试主类（注意类之间继承关系的适用）
##### 2.在测试主类中，实例化多个类实体，模拟学生选课操作、打印课程信息（信息包括：编号、课程名称、上课地点、时间、授课教师 等）；模拟学生退课操作，再打印课程信息。


# 三、实验方法
  ##### 1、先定义人员People类，由题可知，People是student和teacher的父类。
  ##### 2、在定义student和teacher子类通过extend继承父类共有的属性，在定义自己私有的属性和方法，也可使用super直接调用父类的方法。
  ##### 3、在Course类中用tostring直接返回需要的编号，名字等字符串形式
  ##### 4、使用Test类，输入学生信息，老师信息，和选课结果。
  
# 四、流程图

![流程图]https://github.com/wangruifengwrf/Javashiyan-/blob/main/%E6%B5%81%E7%A8%8B%E5%9B%BE.png


# 五、核心代码
```
public class Test {
    public static void main (String[] args){
        Teacher tea1 = new Teacher(000,"吴彦祖","男","离散");
        Teacher tea2 = new Teacher(001,"彭于晏","男","语文");
    	System.out.println("课程信息已更新");
        System.out.println("——————————————————————————————————————————————");
        System.out.println(tea1);
        System.out.println(tea2);
        System.out.println("——————————————————————————————————————————————");  
        Student stu1 = new Student(2019310002,"小明","男");
        Student stu2 = new Student(2019310003,"小红","女");
        System.out.println(stu1);
        System.out.println(stu2);
        System.out.println("选课：");
        System.out.println("——————————————————————————————————————————————");
        Course cou1 = new Course(1,"离散","综合楼","周一");
        Course cou2 = new Course(2,"语文","体育场","周二");
        cou1.setTeacher(tea1.name);
        cou2.setTeacher(tea2.name);
        cou1.choose(stu2.name);
        stu2.setselectcourse(cou1.name);
        cou2.choose(stu1.name);
        stu1.setselectcourse(cou2.name);
        System.out.println(cou1);
        System.out.println(cou2);
        System.out.println("——————————————————————————————————————————————");
        System.out.println("小明退课：");
        cou2.student = "无";
        stu1.selectcourse = "无";
        cou1.drop(stu1.name,cou2.name);
        System.out.println(cou1);
        System.out.println(cou2);
    }
}



```

# 六、结果截图
![结果](https://github.com/wangruifengwrf/Javashiyan-/blob/main/%E7%BB%93%E6%9E%9C.png)
# 七、
加深自己对父类与子类的理解，对于继承的使用。同时学会使用tostring方法。在返回值的时候要以字符串类型，可以加“”来实现转化为字符串输出。在编写extend继承关系的时候，也对super有一些理解，可以直接引用父类的属性方法，进一步的简化程序的编写。
