# generate-test-cases
依据约束条件生成大量测试样例

------

比如你想要生成一个包含a,b,c,d四个变量的测试样例，其中要求的约束有"5<a<10", "a+b>4", "2*b-c^2<=10", "GAUSSIAN(d,1.0,1.0)"，其中a、b要求为int类型，c、d要求为double类型。那么程序要求的输入有：

* 二维列表A=

   1   0   0   0   0 
   
   1   1   0   0   0 
   
   0   1   1   0   0 
    
   0   0   0   1   0 
   
   0   0   1   1   0 


  每个约束代表矩阵中的一行，每个变量代表一列，每一条约束中包含哪个变量就将对应的位置标1，其余位置标0。额外在最后添加一行代表变量类型，int为0，double为1。额外在最后添加一列0，是历史原因造成的，不想改了

* 约束列表constraints=["5<a<10", "a+b>4", "2*b-c^2<=10", "GAUSSIAN(d,1.0,1.0)"]

* 变量名列表symbols=["a","b","c","d"]

* 生成用例个数
