# 编译报错

1.

```
fatal error: backward.hpp: 没有那个文件或目录 #include “backward.hpp”
```

**解决办法：**

修改～/imuCali_ws/src/code_utils/src/sumpixel_test.hpp文件中的头文件为：

```
#include "code_utils/backward.hpp"
```


---

2.

```
/home/office2004/catkin_ws/code_utils-master/src/src/mat_io_test.cpp: In function ‘int main()’:
/home/office2004/catkin_ws/code_utils-master/src/src/mat_io_test.cpp:33:47: error: ‘CV_LOAD_IMAGE_UNCHANGED’ was not declared in this scope
   33 |     Mat img1 = imread( "/home/gao/IMG_1.png", CV_LOAD_IMAGE_UNCHANGED );
      |                                               ^~~~~~~~~~~~~~~~~~~~~~~
/home/office2004/catkin_ws/code_utils-master/src/src/sumpixel_test.cpp: In function ‘void test1()’:
/home/office2004/catkin_ws/code_utils-master/src/src/sumpixel_test.cpp:84:47: error: ‘CV_LOAD_IMAGE_GRAYSCALE’ was not declared in this scope
   84 |     Mat img1 = imread( "/home/gao/IMG_1.png", CV_LOAD_IMAGE_GRAYSCALE );
      |                                               ^~~~~~~~~~~~~~~~~~~~~~~
/home/office2004/catkin_ws/code_utils-master/src/src/sumpixel_test.cpp:94:35: error: ‘CV_MINMAX’ was not declared in this scope; did you mean ‘CV_MMX’?
   94 |     normalize( img, img2, 0, 255, CV_MINMAX );
      |                                   ^~~~~~~~~

```

**解决方案：**

打开出错的源文件，例如 mat_io_test.cpp 和 sumpixel_test.cpp，然后进行如下替换：

将 CV_LOAD_IMAGE_UNCHANGED 替换为 cv::IMREAD_UNCHANGED

将 CV_LOAD_IMAGE_GRAYSCALE 替换为 cv::IMREAD_GRAYSCALE

将 CV_MINMAX 替换为 cv::NORM_MINMAX
