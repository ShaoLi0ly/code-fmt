## 代码规范 <sub>(代码使用php示例)</sub>

### 一. 代码
1. 普通变量命名必须要有意义，使用小写开头，使用驼峰命名，例如：
    ``` php
    // 正例
    $hikeName = "谢小礼";

    // 反例
    $hn = "谢小礼";
    ```
2. ```function```命名必须要有意义，使用小写开头，使用驼峰命名，例如：
    ``` php
    // 正例
    function getHikeName() {}

    // 反例
    function getn() {}
    ```
3. ```phalcon``` 部分需要**暴露接口**的方法在遵循上方规则的同时需要添加Action后缀
    ``` php
    // 正例
    function getHikeNameAction() {}
    
    // 反例
    function gethikenameaction() {}
    ```
4. 类命名必须要有意义，使用大写开头，使用驼峰命名，例如：
    ``` php
    // 正例
    class HikeActivity {}

    // 反例
    function hikeactivity() {}
    ```
5. ```phalcon``` 需要**暴露接口**的类在遵循上方规则的同时需要添加Controller后缀,并且首字母和Controller首字母必须大写，其余字母不允许大写
    ``` php
    // 正例
    class HikeactivityController() {}
    
    // 反例
    class HikeActivityController() {}
    ```
6. 常量命名全部大写，使用下划线```_```分隔，需要在后面添加注释，例如：
    ``` php
    const BILL_ITEM_TYPE_INCOME = 1; // 收入
    ```
7. 方法的变量使用空格分开，例如：
    ``` php
    // 正例
    function createPayment($hiker, $type, $businessNos, $name, $desc, $money, $businessTypes, $bankNo = null, $type_channel = 1) {}

    // 反例
    function createPayment($hiker,$type,$businessNos,$name,$desc,$money,$businessTypes,$bankNo=null,$type_channel=1) {}
    ```
8. 赋值操作符（```=```，```+=``` 等）、逻辑操作符（```&&```，```||```）、等号操作符（```==```，```!=```）、关系运算符（```<```，```>```，```<=```，```>=```）等 需要左右各有一个空格
    例如：
    ``` php
    // 正例
    $num = 1;
    if ($num == 2) {}

    // 反例
    $num=1;
    if($num==2){}
    ```
9. 不要使用意义不明的数值，尽可能使用常量，例如：```status```字段的更新，不要使用```0```和```1```，使用自定义的常量```STATUS_OFF```和```STATUS_ON```
10. ```true/false```的判定不要使用```0/1```替代
11. 一个```function```只做一个用途，如果有多个用途请拆分为多个```function```，例如：一个```function```需要返回一个由多个数组合并排序后的数组，请拆分为数组合并和数组排序两个```function```，然后通过这个```function```调用
12. 文件必须使用```不带BOM的UTF-8```编码
13. 每行代码的长度尽可能的控制在120字符之内，保证可读性
14. 使用4空格缩进

### 二. 注释
1. 方法头注释
    1. 必须包含描述
    2. 必须包含作者
    3. 必须包含时间
    例如：
    ``` php
    // 正例
    /**
     * [getDataByAid 根据活动获取数据]
     * @Author   xsl
     * @DateTime 2018-02-23
     * @Modify 修复通通过实物审核前端无反馈的问题 by xsl 20180306
     */

    // 反例
    /**
    *[getDataByAid]
    */
    ```
2. 方法内新增、修改代码注释一定要标注修改功能、修改人和时间
    1. 必须包含描述
    2. 必须包含作者
    3. 必须包含时间
    4. // 后面需要加一个空格
    例如：
    ``` php
    // 正例
    // 规则更改，公司员工带队境外活动仍然获取100/天补贴 by xsl 2017041

    // 反例
    //规则更改
    ```

### 三. 其他
1. 数据库、数据库表、数据库字段命名全部小写，使用_分隔，例如：```hike_activity```
2. 代码根据功能或者业务分好目录，比如工具放到```utils```，插件放到```plugins```
