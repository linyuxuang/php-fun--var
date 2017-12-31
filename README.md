
# php_fun_var
php函数与变量，回调

              /*  PHP的变量的范围
               *	局部变量： 在函数中声明的变量就是局部变量，只能在自己的函数内部使用。
               *	全局变量：
               *
               *
               *
               */

                function demo(){
                  $a=100;
                }

                demo();
                demo();
                demo();
                demo();
                demo();
                demo();

                echo $a."<br>";

                function test(){
                  echo $a."<br>";
                }

                test();


             *	局部变量： 在函数中声明的变量就是局部变量，只能在自己的函数内部使用。
             *	全局变量： 在函数外声明，在变量声明以后的，直到整个脚本结束前都可以使用,包括在函数中和｛｝中都可使用
             *    
             *      PHP的变量分不出 是声明还是使用, 
             *      在PHP中使用全局变量 要通过global关键字将这个全局变量包括到函数中才能使用到，在global声明之后才是使用全局的变量
             *
             *
             */

            $a=10;


            function demo(){
              global $a;
              $a+=10;
              echo $a." demo<br>";
            }

            function test(){
              global $a;
              $a+=5;
              echo $a." test<br>";
            }

            echo $a."----<br>";
            demo();
            echo $a."!!!!<br>";
            demo();
            echo $a."@@@@@<br>";
            test();
            echo $a."#######<br>";


                 /*  PHP的变量的范围
                     *	局部变量： 在函数中声明的变量就是局部变量，只能在自己的函数内部使用。
                     *	全局变量： 在函数外声明，在变量声明以后的，直到整个脚本结束前都可以使用,包括在函数中和｛｝中都可使用
                     *    
                     *      PHP的变量分不出 是声明还是使用, 
                     *      在PHP中使用全局变量 要通过global关键字将这个全局变量包括到函数中才能使用到，在global声明之后才是使用全局的变量
                     *
                     *     参数就是局部变量，这个局部变量可以调用 时去赋值。
                     */

                    $a=10;


                    function demo($a){
                      $a+=5;

                    }

                    function test($b){
                      $b+=10;
                    }

                    demo($a);
                    test($a);


                    echo $a;




                 /*  PHP的变量的范围
                 *	局部变量： 在函数中声明的变量就是局部变量，只能在自己的函数内部使用。
                 *	全局变量： 在函数外声明，在变量声明以后的，直到整个脚本结束前都可以使用,包括在函数中和｛｝中都可使用
                 *    
                 *      PHP的变量分不出 是声明还是使用, 
                 *      在PHP中使用全局变量 要通过global关键字将这个全局变量包括到函数中才能使用到，在global声明之后才是使用全局的变量
                 *
                 *     参数就是局部变量，这个局部变量可以调用 时去赋值。
                 *
                 *  PHP的静态变量
                 *
                 *  	静态变量只能声明在函数中（类中），不能在全局声明
                 *  	使用static在变量前；
                 *
                 *  	作用：一个变量可以在同一个函数在多次调用中同用。
                 *  	     1. 静态变量在静态代码段中保存
                 *  	     2. 一个函数多次调用之间共用，但只在第一次调用 函数时声明到内存，以后再调用用，就不再声明，而直接使用
                 */


                   function test(){
                    static $a=0;

                  $a++;

                  echo $a."<br>";
                   }

                  test();
                  test();
                  test();
                  test();
                  test();
                  test();
                  test();
                  test();
                  test();
                  test();
                  test();
                  test();


         
               *
               *  变量函数：如果一个变量后面有括号$var=hello  $var(), 就将寻找与变量值同名的函数 hello();
               *
               */

                function one($a, $b){
                  return $a+$b;
                }

                function two($a, $b){
                return $a*$a+$b*$b; 
                }

                function three($a, $b){
                  return $a*$a*$a+$b*$b*$b;
                }


                $var=one;
                $var="two";
                $var=three;

                echo "结果：".$var(3, 4)."<br>";


                       *
                       *  1. 函数的功能------------决定是否使用这个函数
                       *  2. 函数的参数------------决定函数怎么调用 ---有几个参，传什么类型的值，。。。。
                       *  3. 函数的返回值----------调用后怎么处理这个函数
                       *
                       *  PHP给2000多个函数。。。 都属于系统涵 数，都可以通过名称直接使用。
                       *
                       *  一定要先使用系统函数，如果系统函数没有你想要的功能，再去自己定义函数
                       *
                       *  1. 常规函数  
                        bool copy ( string source, string dest ) 
                          2. 带有mixed , mixed表示可以传任何类型的数据 
                             bool chown ( string filename, mixed user )
                          3. 带有&参数的函数， 表示引用赋值， 这个参数不能传值，只能传一个变量，然后函数将变量的值改变，我们在使用这个变量时，值也是变化的
                        bool arsort ( array &array [, int sort_flags] )


                         $arr=array(1, 9, 5, 8, 3, 4);

                        sort($arr);

                        print_r($arr);



                    4.默认函数 带有[]的函数, 表示这个参数是可选的，如果你传值了就使用你传的值，如果没有传值则使用默认值
                    直接在声明函数时，就为参数给初值。
                    可选值和必须值， 必须从后向前设置
                  bool arsort ( array &array [, int sort_flags] )


                
                   function demo($a=1, $b=20, $c){
                    echo "### $a ### $b ##### $c ########<br>";
                   }	

                   demo(8,9);


  

                          5. 带有...的参数函数， ...表示可以传任意多个参数
                        int array_unshift ( array &array, mixed var [, mixed ...] )
                        

                        function demo(){
                          $args=func_get_args();
                          $sum=0;
                          for($i=0; $i<count($args); $i++){
                            $sum+=$args[$i];
                          }

                          return $sum;
                        }


                       echo  demo(1, 2, 3, 4, 5, 6, 7,8,9);
   
 

                       6. 回调函数 带有callback,  就是调用这个函数时需要我们传一个函数进来（函数名，函数名字串）
                           array array_filter ( array input [, callback callback] )


                      function demo($x, $y){
                        return $x*$y;
                      }

                      function test($x, $y){
                        return $x*$x + $y*$y;
                      }

                       function sum($a, $b, $fun){

                        return $a+$b+$fun($a,$b);

                       }

                      echo sum(2, 3, demo);
                      echo sum(2, 4, "test");




                        $a=array(1, 2, -3,4,-5,6,-7,8,9);

                        print_r(array_filter($a, demo));


                         function demo($n){
                          if($n%2== 0)
                          return true;
                        else
                          return false;
                         }




          
        
  *  2. 递归函数: 就是在自己内部调用自己的函数名
  *
 

                    function demo($num){
                      echo $num."<br>";

                  if($num>0)
                    demo($num-1);
                  else
                    echo "--------------------<br>";

                  echo $num."<br>";
                    }

                    demo(10);



                function total($dirname, &$dirnum, &$filenum){
                $dir=opendir($dirname);
                readdir($dir)."<br>";
                readdir($dir)."<br>";
                while($filename=readdir($dir)){
                 $newfile=$dirname."/".$filename;

                 if(is_dir($newfile)){
                 total($newfile, $dirnum, $filenum);  
                     $dirnum++;
                  }else{
                     $filenum++;
                  }
                }
               closedir($dir);	 
              }

             $dirnum=0;
             $filenum=0;
             total("C:/AppServ/www/phpMyAdmin", $dirnum, $filenum);

             echo "目录总数:".$dirnum."<br>";
             echo "文件总数:".$filenum."<br>";
   
         
         



            
  *  3. 重用函数(使用自己定义的函数库)
  *      
  *
                    *      require
                    *      include
                    *      require_once
                    *      include_once
                    *   
                    *      .txt  .html  .php 
                    *
                    *
                    *      include(文件名);
                    *      include "文件名";
                    *      
                    *      echo "@@@@@@@@@@@2";
                    *      echo("@@@@@@@@@@@@@");
                    *      break
                    *      exit;
                    *
                    *     include "config.inc.php";
                    *     include("config.inc.php")
                    *
                    *  4. 一些系统函数的使用
                    *
                    *  
                   *
                    */


                     include_once "test.txt";
                     include_once "test.txt";
                     include_once "test.txt";

                     require_once("test.html");
                     require_once("test.html");
                     require_once("test.html");

                     include "test.inc.php";
                     include_once "test.inc.php";

                     echo $a."<br>";

                     test();

例如



                       require "header.inc.php";
                      if($className=="Action"){
                        include "action/".$className.".php";
                      }elseif($className=="Model"){
                        include "model/".$className.".php";
                      }else{
                        include "public/".$className.".php";
                      }

                      require "footer.inc.php";






