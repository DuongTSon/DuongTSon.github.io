---
title       : Vietnam interest rate forecast model
subtitle    : 
author      : Duong T.Son, Le T.My
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : solarized_light      # 
widgets     : [mathjax, quiz, bootstrap, shiny]
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---


## Nội dung

> 1. Giới thiệu chung về rủi ro vĩ mô
> 2. Lựa chọn mô hình phù hợp cho lãi suất
> 3. Mô hình kinh tế lượng áp dụng đối với xu hướng dài hạn của lãi suất
> 4. Xây dựng mô hình
> 5. Ứng dụng

--- .dark .nobackground .quote

<q>Suy thoái kinh tế xảy ra __trung bình 10 năm 1 lần__ và khủng hoảng ngân hàng xảy ra trung bình 40 năm 1 lần.</q>



--- .bigger

## Giới thiệu chung về rủi ro vĩ mô

- Khủng hoảng tài chính Châu Á:
Đồng Bath mất hơn 50% giá trị, thị trường chứng khoán giảm 75%, công ty tài chính lớn nhất Thái lan phá sản. Nợ xấu tại Hàn quốc tăng mạnh khiến 787 tổ chức tín dụng mất khả năng thanh toán, đồng won giảm gần 1 nửa giá trị thị trường.

- Suy thoái kinh tế 2008-2013 tại Việt Nam:
Lãi suất tăng mạnh do chạy đua tăng trưởng tín dụng; SBV liên tục phá giá VND (có thời điểm SBV phá giá 9.3% trong 1 ngày).

--- .bigger

## Giới thiệu chung về rủi ro vĩ mô

<center>
![plot of chunk bunch_o_figs_svg](assets/fig/bunch_o_figs_svg-1.svg)
</center>

--- &twocol

## Lựa chọn mô hình phù hợp cho lãi suất 

*** =left

<!-- AnnotationChart generated in R 3.3.1 by googleVis 0.6.1 package -->
<!-- Wed Nov 02 08:07:01 2016 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataAnnotationChartIDb2c51d17cd2 () {
var data = new google.visualization.DataTable();
var datajson =
[
 [
new Date(2000,0,1),
10.8,
3.6
],
[
new Date(2000,3,1),
10.8,
3.58
],
[
new Date(2000,6,1),
10.4,
3.54
],
[
new Date(2000,9,1),
10.2,
3.89
],
[
new Date(2001,0,1),
10.65,
5.24
],
[
new Date(2001,3,1),
9.35,
4.96
],
[
new Date(2001,6,1),
9,
5.2
],
[
new Date(2001,9,1),
8.68,
5.82
],
[
new Date(2002,0,1),
8.52,
5.9
],
[
new Date(2002,3,1),
8.75,
6.39
],
[
new Date(2002,6,1),
9.5,
6.7
],
[
new Date(2002,9,1),
9.48,
6.8
],
[
new Date(2003,0,1),
9.41,
6.87
],
[
new Date(2003,3,1),
9.45,
7.04
],
[
new Date(2003,6,1),
9.54,
6.61
],
[
new Date(2003,9,1),
9.52,
5.97
],
[
new Date(2004,0,1),
9.54,
5.97
],
[
new Date(2004,3,1),
9.54,
5.97
],
[
new Date(2004,6,1),
9.68,
6.22
],
[
new Date(2004,9,1),
10.13,
6.53
],
[
new Date(2005,0,1),
10.82,
6.54
],
[
new Date(2005,3,1),
10.88,
7.2
],
[
new Date(2005,6,1),
11.08,
7.31
],
[
new Date(2005,9,1),
11.33,
7.53
],
[
new Date(2006,0,1),
11.18,
7.61
],
[
new Date(2006,3,1),
11.18,
7.61
],
[
new Date(2006,6,1),
11.18,
7.65
],
[
new Date(2006,9,1),
11.18,
7.65
],
[
new Date(2007,0,1),
11.18,
7.67
],
[
new Date(2007,3,1),
11.18,
7.58
],
[
new Date(2007,6,1),
11.18,
7.44
],
[
new Date(2007,9,1),
11.18,
7.28
],
[
new Date(2008,0,1),
12.32,
9.12
],
[
new Date(2008,3,1),
16.64,
13.8
],
[
new Date(2008,6,1),
20.1,
16.99
],
[
new Date(2008,9,1),
14.08,
11.01
],
[
new Date(2009,0,1),
9.54,
6.88
],
[
new Date(2009,3,1),
9.57,
7.33
],
[
new Date(2009,6,1),
10.19,
7.9
],
[
new Date(2009,9,1),
10.98,
9.53
],
[
new Date(2010,0,1),
12,
10.26
],
[
new Date(2010,3,1),
13.44,
11.12
],
[
new Date(2010,6,1),
13.17,
11.1
],
[
new Date(2010,9,1),
13.93,
12.29
],
[
new Date(2011,0,1),
16.05,
13.96
],
[
new Date(2011,3,1),
18.02,
14
],
[
new Date(2011,6,1),
17.91,
14
],
[
new Date(2011,9,1),
15.84,
14
],
[
new Date(2012,0,1),
15.3,
13.65
],
[
new Date(2012,3,1),
13.87,
10.68
],
[
new Date(2012,6,1),
12.49,
9
],
[
new Date(2012,9,1),
12.23,
8.68
],
[
new Date(2013,0,1),
11.85,
7.86
],
[
new Date(2013,3,1),
10.2,
7.04
],
[
new Date(2013,6,1),
9.82,
6.85
],
[
new Date(2013,9,1),
9.63,
6.81
],
[
new Date(2014,0,1),
9.58,
6.42
],
[
new Date(2014,3,1),
8.6,
5.85
],
[
new Date(2014,6,1),
8.32,
5.76
],
[
new Date(2014,9,1),
8.16,
5
],
[
new Date(2015,0,1),
7.23,
4.82
],
[
new Date(2015,3,1),
7.23,
4.72
],
[
new Date(2015,6,1),
7.05,
4.72
],
[
new Date(2015,9,1),
6.96,
4.73
],
[
new Date(2016,0,1),
6.96,
4.99
],
[
new Date(2016,3,1),
6.96,
5.25
],
[
new Date(2016,6,1),
6.76,
5.25
] 
];
data.addColumn('date','quarter');
data.addColumn('number','Lending_rate');
data.addColumn('number','Deposit_rate');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartAnnotationChartIDb2c51d17cd2() {
var data = gvisDataAnnotationChartIDb2c51d17cd2();
var options = {};
options["width"] = 500;
options["height"] = 300;

    var chart = new google.visualization.AnnotationChart(
    document.getElementById('AnnotationChartIDb2c51d17cd2')
    );
    chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
var pkgs = window.__gvisPackages = window.__gvisPackages || [];
var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
var chartid = "annotationchart";
  
// Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
var i, newPackage = true;
for (i = 0; newPackage && i < pkgs.length; i++) {
if (pkgs[i] === chartid)
newPackage = false;
}
if (newPackage)
  pkgs.push(chartid);
  
// Add the drawChart function to the global list of callbacks
callbacks.push(drawChartAnnotationChartIDb2c51d17cd2);
})();
function displayChartAnnotationChartIDb2c51d17cd2() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  window.clearTimeout(window.__gvisLoad);
  // The timeout is set to 100 because otherwise the container div we are
  // targeting might not be part of the document yet
  window.__gvisLoad = setTimeout(function() {
  var pkgCount = pkgs.length;
  google.load("visualization", "1", { packages:pkgs, callback: function() {
  if (pkgCount != pkgs.length) {
  // Race condition where another setTimeout call snuck in after us; if
  // that call added a package, we must not shift its callback
  return;
}
while (callbacks.length > 0)
callbacks.shift()();
} });
}, 100);
}
 
// jsFooter
</script>
 
<!-- jsChart -->  
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartAnnotationChartIDb2c51d17cd2"></script>
 
<!-- divChart -->
  
<div id="AnnotationChartIDb2c51d17cd2" 
  style="width: 500; height: 300;">
</div>


<br/>

* Bị ảnh hưởng bởi chu kỳ kinh tế
* Ít biến động trong ngắn hạn
* Có thể dự báo bằng các yếu tố vĩ mô


*** =right

<!-- AnnotationChart generated in R 3.3.1 by googleVis 0.6.1 package -->
<!-- Wed Nov 02 08:07:01 2016 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataAnnotationChartIDb2c7b5c753d () {
var data = new google.visualization.DataTable();
var datajson =
[
 [
new Date(2013,10,15),
3.88
],
[
new Date(2013,10,18),
3.76
],
[
new Date(2013,10,19),
3.6
],
[
new Date(2013,10,20),
3.34
],
[
new Date(2013,10,21),
3.34
],
[
new Date(2013,10,22),
3.34
],
[
new Date(2013,10,25),
3.8
],
[
new Date(2013,10,26),
3.8
],
[
new Date(2013,10,27),
3.42
],
[
new Date(2013,10,28),
3.08
],
[
new Date(2013,10,29),
2.34
],
[
new Date(2013,11,2),
3.46
],
[
new Date(2013,11,3),
3.12
],
[
new Date(2013,11,4),
2.64
],
[
new Date(2013,11,5),
2.4
],
[
new Date(2013,11,6),
2.28
],
[
new Date(2013,11,9),
2.16
],
[
new Date(2013,11,10),
2.16
],
[
new Date(2013,11,11),
2.58
],
[
new Date(2013,11,12),
2.58
],
[
new Date(2013,11,13),
2.46
],
[
new Date(2013,11,16),
2.34
],
[
new Date(2013,11,17),
2.38
],
[
new Date(2013,11,18),
2.38
],
[
new Date(2013,11,19),
2.38
],
[
new Date(2013,11,20),
2.38
],
[
new Date(2013,11,23),
3.34
],
[
new Date(2013,11,24),
4.26
],
[
new Date(2013,11,25),
4.02
],
[
new Date(2013,11,26),
4.4
],
[
new Date(2013,11,27),
3.76
],
[
new Date(2013,11,30),
3.76
],
[
new Date(2013,11,31),
3.76
],
[
new Date(2014,0,2),
3.76
],
[
new Date(2014,0,3),
3.56
],
[
new Date(2014,0,6),
3.56
],
[
new Date(2014,0,7),
3.96
],
[
new Date(2014,0,8),
4.2
],
[
new Date(2014,0,9),
4.28
],
[
new Date(2014,0,10),
4.28
],
[
new Date(2014,0,13),
4.7
],
[
new Date(2014,0,14),
4.9
],
[
new Date(2014,0,15),
4.72
],
[
new Date(2014,0,16),
4.34
],
[
new Date(2014,0,17),
3.78
],
[
new Date(2014,0,20),
3.32
],
[
new Date(2014,0,21),
4.4
],
[
new Date(2014,0,22),
4.64
],
[
new Date(2014,0,23),
5.3
],
[
new Date(2014,0,24),
5.3
],
[
new Date(2014,0,25),
5.3
],
[
new Date(2014,0,27),
5.3
],
[
new Date(2014,1,6),
3.66
],
[
new Date(2014,1,7),
3.28
],
[
new Date(2014,1,8),
3.28
],
[
new Date(2014,1,10),
3.04
],
[
new Date(2014,1,11),
2.28
],
[
new Date(2014,1,12),
2.08
],
[
new Date(2014,1,13),
1.96
],
[
new Date(2014,1,14),
1.72
],
[
new Date(2014,1,17),
1.74
],
[
new Date(2014,1,18),
1.72
],
[
new Date(2014,1,19),
1.62
],
[
new Date(2014,1,20),
1.52
],
[
new Date(2014,1,21),
1.5
],
[
new Date(2014,1,24),
1.5
],
[
new Date(2014,1,25),
1.66
],
[
new Date(2014,1,26),
2.18
],
[
new Date(2014,1,27),
1.86
],
[
new Date(2014,1,28),
1.7
],
[
new Date(2014,2,3),
1.86
],
[
new Date(2014,2,4),
1.86
],
[
new Date(2014,2,5),
2
],
[
new Date(2014,2,6),
2
],
[
new Date(2014,2,7),
2
],
[
new Date(2014,2,10),
2.54
],
[
new Date(2014,2,11),
2.54
],
[
new Date(2014,2,12),
2.12
],
[
new Date(2014,2,13),
2.08
],
[
new Date(2014,2,14),
1.46
],
[
new Date(2014,2,17),
1.34
],
[
new Date(2014,2,18),
1.4
],
[
new Date(2014,2,19),
1.64
],
[
new Date(2014,2,20),
1.78
],
[
new Date(2014,2,21),
1.88
],
[
new Date(2014,2,24),
1.9
],
[
new Date(2014,2,25),
1.92
],
[
new Date(2014,2,26),
1.92
],
[
new Date(2014,2,27),
1.92
],
[
new Date(2014,2,28),
2.02
],
[
new Date(2014,2,31),
2.02
],
[
new Date(2014,3,1),
2.1
],
[
new Date(2014,3,2),
2.36
],
[
new Date(2014,3,3),
2.42
],
[
new Date(2014,3,4),
2.42
],
[
new Date(2014,3,7),
2.42
],
[
new Date(2014,3,8),
2.42
],
[
new Date(2014,3,10),
2.42
],
[
new Date(2014,3,11),
2.42
],
[
new Date(2014,3,14),
2.42
],
[
new Date(2014,3,15),
2.36
],
[
new Date(2014,3,16),
2.36
],
[
new Date(2014,3,17),
2.36
],
[
new Date(2014,3,18),
1.74
],
[
new Date(2014,3,21),
1.9
],
[
new Date(2014,3,22),
1.9
],
[
new Date(2014,3,23),
1.9
],
[
new Date(2014,3,24),
1.9
],
[
new Date(2014,3,25),
1.9
],
[
new Date(2014,3,26),
1.9
],
[
new Date(2014,3,28),
1.98
],
[
new Date(2014,3,29),
2.92
],
[
new Date(2014,4,5),
3.3
],
[
new Date(2014,4,6),
3.3
],
[
new Date(2014,4,7),
3
],
[
new Date(2014,4,8),
3
],
[
new Date(2014,4,9),
2.3
],
[
new Date(2014,4,12),
2.64
],
[
new Date(2014,4,13),
3.94
],
[
new Date(2014,4,14),
3.24
],
[
new Date(2014,4,15),
3.36
],
[
new Date(2014,4,16),
3.64
],
[
new Date(2014,4,19),
3.9
],
[
new Date(2014,4,20),
3.88
],
[
new Date(2014,4,21),
4.02
],
[
new Date(2014,4,22),
3.98
],
[
new Date(2014,4,23),
3.46
],
[
new Date(2014,4,26),
3.4
],
[
new Date(2014,4,27),
3.4
],
[
new Date(2014,4,28),
2.68
],
[
new Date(2014,4,29),
1.86
],
[
new Date(2014,4,30),
1.66
],
[
new Date(2014,5,2),
2.58
],
[
new Date(2014,5,3),
2.42
],
[
new Date(2014,5,4),
2.2
],
[
new Date(2014,5,5),
2.28
],
[
new Date(2014,5,6),
2.2
],
[
new Date(2014,5,9),
2.2
],
[
new Date(2014,5,10),
2.2
],
[
new Date(2014,5,11),
2.26
],
[
new Date(2014,5,12),
2.28
],
[
new Date(2014,5,13),
2.3
],
[
new Date(2014,5,16),
2.3
],
[
new Date(2014,5,17),
2.82
],
[
new Date(2014,5,18),
2.48
],
[
new Date(2014,5,19),
2.44
],
[
new Date(2014,5,20),
2.42
],
[
new Date(2014,5,23),
2.4
],
[
new Date(2014,5,24),
2.4
],
[
new Date(2014,5,25),
2.4
],
[
new Date(2014,5,26),
2.4
],
[
new Date(2014,5,27),
2.4
],
[
new Date(2014,5,30),
2.4
],
[
new Date(2014,6,1),
2.44
],
[
new Date(2014,6,2),
2.34
],
[
new Date(2014,6,3),
2.3
],
[
new Date(2014,6,4),
2.3
],
[
new Date(2014,6,7),
2.12
],
[
new Date(2014,6,8),
2.5
],
[
new Date(2014,6,9),
2.5
],
[
new Date(2014,6,10),
2.5
],
[
new Date(2014,6,11),
2.66
],
[
new Date(2014,6,14),
2.96
],
[
new Date(2014,6,15),
2.3
],
[
new Date(2014,6,16),
2.3
],
[
new Date(2014,6,17),
2.3
],
[
new Date(2014,6,18),
2.32
],
[
new Date(2014,6,21),
2.8
],
[
new Date(2014,6,22),
2.96
],
[
new Date(2014,6,23),
3.06
],
[
new Date(2014,6,24),
2.9
],
[
new Date(2014,6,25),
2.66
],
[
new Date(2014,6,28),
2.5
],
[
new Date(2014,6,29),
2.5
],
[
new Date(2014,6,30),
2.5
],
[
new Date(2014,6,31),
2.48
],
[
new Date(2014,7,1),
2.82
],
[
new Date(2014,7,4),
2.94
],
[
new Date(2014,7,5),
3.16
],
[
new Date(2014,7,6),
3.16
],
[
new Date(2014,7,7),
3.12
],
[
new Date(2014,7,8),
3.16
],
[
new Date(2014,7,11),
3.68
],
[
new Date(2014,7,12),
3.94
],
[
new Date(2014,7,13),
3.92
],
[
new Date(2014,7,14),
3.66
],
[
new Date(2014,7,15),
3.66
],
[
new Date(2014,7,18),
3.66
],
[
new Date(2014,7,19),
3.66
],
[
new Date(2014,7,20),
4
],
[
new Date(2014,7,21),
4.08
],
[
new Date(2014,7,22),
4.08
],
[
new Date(2014,7,25),
3.92
],
[
new Date(2014,7,26),
3.88
],
[
new Date(2014,7,27),
3.9
],
[
new Date(2014,7,28),
3.88
],
[
new Date(2014,7,29),
3.76
],
[
new Date(2014,8,3),
3.68
],
[
new Date(2014,8,4),
3.42
],
[
new Date(2014,8,5),
3.48
],
[
new Date(2014,8,8),
2.96
],
[
new Date(2014,8,9),
2.76
],
[
new Date(2014,8,10),
2.24
],
[
new Date(2014,8,11),
2.04
],
[
new Date(2014,8,12),
1.78
],
[
new Date(2014,8,15),
1.98
],
[
new Date(2014,8,16),
1.98
],
[
new Date(2014,8,17),
1.98
],
[
new Date(2014,8,18),
1.78
],
[
new Date(2014,8,19),
1.68
],
[
new Date(2014,8,22),
1.86
],
[
new Date(2014,8,23),
1.86
],
[
new Date(2014,8,24),
1.76
],
[
new Date(2014,8,25),
1.76
],
[
new Date(2014,8,26),
1.66
],
[
new Date(2014,8,29),
1.66
],
[
new Date(2014,8,30),
1.66
],
[
new Date(2014,9,1),
1.9
],
[
new Date(2014,9,2),
1.7
],
[
new Date(2014,9,3),
1.66
],
[
new Date(2014,9,6),
1.66
],
[
new Date(2014,9,7),
1.66
],
[
new Date(2014,9,8),
1.8
],
[
new Date(2014,9,9),
1.92
],
[
new Date(2014,9,10),
2.2
],
[
new Date(2014,9,13),
2.96
],
[
new Date(2014,9,14),
2.96
],
[
new Date(2014,9,15),
2.96
],
[
new Date(2014,9,16),
2.54
],
[
new Date(2014,9,17),
2.38
],
[
new Date(2014,9,20),
3.02
],
[
new Date(2014,9,21),
3.52
],
[
new Date(2014,9,22),
3.46
],
[
new Date(2014,9,23),
3.54
],
[
new Date(2014,9,24),
2.74
],
[
new Date(2014,9,27),
2.26
],
[
new Date(2014,9,28),
1.86
],
[
new Date(2014,9,29),
1.16
],
[
new Date(2014,9,30),
1.16
],
[
new Date(2014,9,31),
1.16
],
[
new Date(2014,10,3),
2.28
],
[
new Date(2014,10,4),
2.18
],
[
new Date(2014,10,5),
2.06
],
[
new Date(2014,10,6),
2.06
],
[
new Date(2014,10,7),
2.06
],
[
new Date(2014,10,10),
2.5
],
[
new Date(2014,10,11),
3.28
],
[
new Date(2014,10,12),
3.48
],
[
new Date(2014,10,13),
3.56
],
[
new Date(2014,10,14),
3.48
],
[
new Date(2014,10,17),
3.48
],
[
new Date(2014,10,18),
3.76
],
[
new Date(2014,10,19),
3.82
],
[
new Date(2014,10,20),
3.66
],
[
new Date(2014,10,21),
3.58
],
[
new Date(2014,10,24),
3.48
],
[
new Date(2014,10,25),
3.38
],
[
new Date(2014,10,26),
3.56
],
[
new Date(2014,10,27),
3.54
],
[
new Date(2014,10,28),
3.3
],
[
new Date(2014,10,29),
3.3
],
[
new Date(2014,11,1),
3.56
],
[
new Date(2014,11,2),
3.78
],
[
new Date(2014,11,3),
3.94
],
[
new Date(2014,11,4),
3.9
],
[
new Date(2014,11,5),
3.94
],
[
new Date(2014,11,8),
4.1
],
[
new Date(2014,11,9),
4.32
],
[
new Date(2014,11,10),
4.5
],
[
new Date(2014,11,11),
4.4
],
[
new Date(2014,11,12),
4.02
],
[
new Date(2014,11,15),
3.96
],
[
new Date(2014,11,16),
3.56
],
[
new Date(2014,11,17),
3.32
],
[
new Date(2014,11,18),
2.78
],
[
new Date(2014,11,19),
2.66
],
[
new Date(2014,11,22),
3.96
],
[
new Date(2014,11,23),
4.3
],
[
new Date(2014,11,24),
3.92
],
[
new Date(2014,11,25),
3.7
],
[
new Date(2014,11,26),
3.7
],
[
new Date(2014,11,29),
3.64
],
[
new Date(2014,11,30),
3.46
],
[
new Date(2014,11,31),
4.22
],
[
new Date(2015,0,5),
4.1
],
[
new Date(2015,0,6),
3.98
],
[
new Date(2015,0,7),
3.74
],
[
new Date(2015,0,8),
3.74
],
[
new Date(2015,0,9),
3.74
],
[
new Date(2015,0,12),
3.8
],
[
new Date(2015,0,13),
3.78
],
[
new Date(2015,0,14),
3.78
],
[
new Date(2015,0,15),
3.78
],
[
new Date(2015,0,16),
3.78
],
[
new Date(2015,0,19),
3.78
],
[
new Date(2015,0,20),
3.72
],
[
new Date(2015,0,21),
3.72
],
[
new Date(2015,0,22),
3.7
],
[
new Date(2015,0,23),
3.64
],
[
new Date(2015,0,26),
3.74
],
[
new Date(2015,0,27),
3.74
],
[
new Date(2015,0,28),
3.74
],
[
new Date(2015,0,29),
3.74
],
[
new Date(2015,0,30),
3.64
],
[
new Date(2015,1,2),
4.76
],
[
new Date(2015,1,3),
4.76
],
[
new Date(2015,1,4),
4.64
],
[
new Date(2015,1,5),
4.64
],
[
new Date(2015,1,6),
4.88
],
[
new Date(2015,1,9),
4.96
],
[
new Date(2015,1,10),
4.96
],
[
new Date(2015,1,11),
4.88
],
[
new Date(2015,1,12),
4.86
],
[
new Date(2015,1,13),
4.96
],
[
new Date(2015,1,14),
4.96
],
[
new Date(2015,1,23),
4.8
],
[
new Date(2015,1,24),
4.8
],
[
new Date(2015,1,25),
3.96
],
[
new Date(2015,1,26),
3.86
],
[
new Date(2015,1,27),
3.52
],
[
new Date(2015,2,2),
3.5
],
[
new Date(2015,2,3),
3.6
],
[
new Date(2015,2,4),
3.6
],
[
new Date(2015,2,5),
3.56
],
[
new Date(2015,2,6),
4.14
],
[
new Date(2015,2,9),
4.68
],
[
new Date(2015,2,10),
4.92
],
[
new Date(2015,2,11),
4.5
],
[
new Date(2015,2,12),
4.2
],
[
new Date(2015,2,13),
4.2
],
[
new Date(2015,2,16),
4.14
],
[
new Date(2015,2,17),
4.22
],
[
new Date(2015,2,18),
4.22
],
[
new Date(2015,2,19),
4.26
],
[
new Date(2015,2,20),
4.28
],
[
new Date(2015,2,23),
4.54
],
[
new Date(2015,2,24),
4.54
],
[
new Date(2015,2,25),
4.84
],
[
new Date(2015,2,26),
4.84
],
[
new Date(2015,2,27),
4.6
],
[
new Date(2015,2,30),
3.92
],
[
new Date(2015,2,31),
3.56
],
[
new Date(2015,3,1),
3.88
],
[
new Date(2015,3,2),
3.84
],
[
new Date(2015,3,3),
3.66
],
[
new Date(2015,3,6),
3.12
],
[
new Date(2015,3,7),
3.12
],
[
new Date(2015,3,8),
3.76
],
[
new Date(2015,3,9),
4.58
],
[
new Date(2015,3,10),
4.72
],
[
new Date(2015,3,13),
4.86
],
[
new Date(2015,3,14),
4.98
],
[
new Date(2015,3,15),
5.16
],
[
new Date(2015,3,16),
5.16
],
[
new Date(2015,3,17),
5.16
],
[
new Date(2015,3,20),
5.3
],
[
new Date(2015,3,21),
5.18
],
[
new Date(2015,3,22),
5.18
],
[
new Date(2015,3,23),
4.9
],
[
new Date(2015,3,24),
3.9
],
[
new Date(2015,3,27),
4.28
],
[
new Date(2015,4,4),
4.3
],
[
new Date(2015,4,5),
4.92
],
[
new Date(2015,4,6),
4.92
],
[
new Date(2015,4,7),
4.06
],
[
new Date(2015,4,8),
3.66
],
[
new Date(2015,4,11),
3.46
],
[
new Date(2015,4,12),
3.26
],
[
new Date(2015,4,13),
3.32
],
[
new Date(2015,4,14),
3.46
],
[
new Date(2015,4,15),
3.46
],
[
new Date(2015,4,18),
3.46
],
[
new Date(2015,4,19),
3.32
],
[
new Date(2015,4,20),
3.04
],
[
new Date(2015,4,21),
2.66
],
[
new Date(2015,4,22),
2.32
],
[
new Date(2015,4,25),
2.32
],
[
new Date(2015,4,26),
1.96
],
[
new Date(2015,4,27),
1.62
],
[
new Date(2015,4,28),
1.62
],
[
new Date(2015,4,29),
1.52
],
[
new Date(2015,5,1),
2.38
],
[
new Date(2015,5,2),
3.16
],
[
new Date(2015,5,3),
3.44
],
[
new Date(2015,5,4),
3.48
],
[
new Date(2015,5,5),
3.62
],
[
new Date(2015,5,8),
4.34
],
[
new Date(2015,5,9),
4.4
],
[
new Date(2015,5,10),
4.48
],
[
new Date(2015,5,11),
4.56
],
[
new Date(2015,5,12),
4.62
],
[
new Date(2015,5,15),
4.48
],
[
new Date(2015,5,16),
4.3
],
[
new Date(2015,5,17),
3.6
],
[
new Date(2015,5,18),
3.58
],
[
new Date(2015,5,19),
3.58
],
[
new Date(2015,5,22),
3.36
],
[
new Date(2015,5,23),
2.98
],
[
new Date(2015,5,24),
2.98
],
[
new Date(2015,5,25),
2.48
],
[
new Date(2015,5,26),
2.68
],
[
new Date(2015,5,29),
2.68
],
[
new Date(2015,5,30),
2.98
],
[
new Date(2015,6,1),
3.38
],
[
new Date(2015,6,2),
3.4
],
[
new Date(2015,6,3),
3.4
],
[
new Date(2015,6,6),
3.3
],
[
new Date(2015,6,7),
3.08
],
[
new Date(2015,6,8),
2.84
],
[
new Date(2015,6,9),
2.3
],
[
new Date(2015,6,10),
2.26
],
[
new Date(2015,6,13),
2.2
],
[
new Date(2015,6,14),
2.24
],
[
new Date(2015,6,15),
2.28
],
[
new Date(2015,6,16),
2.22
],
[
new Date(2015,6,17),
2.08
],
[
new Date(2015,6,20),
1.96
],
[
new Date(2015,6,21),
1.96
],
[
new Date(2015,6,22),
2.1
],
[
new Date(2015,6,23),
2.22
],
[
new Date(2015,6,24),
2.22
],
[
new Date(2015,6,27),
2.7
],
[
new Date(2015,6,28),
2.82
],
[
new Date(2015,6,29),
3
],
[
new Date(2015,6,30),
3.38
],
[
new Date(2015,6,31),
3.96
],
[
new Date(2015,7,3),
4.42
],
[
new Date(2015,7,4),
4.2
],
[
new Date(2015,7,5),
3.64
],
[
new Date(2015,7,6),
3.4
],
[
new Date(2015,7,7),
3.4
],
[
new Date(2015,7,10),
3.4
],
[
new Date(2015,7,11),
3.8
],
[
new Date(2015,7,12),
4.8
],
[
new Date(2015,7,13),
4.8
],
[
new Date(2015,7,14),
4.8
],
[
new Date(2015,7,17),
4.92
],
[
new Date(2015,7,18),
5.12
],
[
new Date(2015,7,19),
4.92
],
[
new Date(2015,7,20),
4.92
],
[
new Date(2015,7,21),
4.92
],
[
new Date(2015,7,24),
5.14
],
[
new Date(2015,7,25),
5.14
],
[
new Date(2015,7,26),
4.44
],
[
new Date(2015,7,27),
4.76
],
[
new Date(2015,7,28),
3.88
],
[
new Date(2015,7,31),
3.64
],
[
new Date(2015,8,1),
4.04
],
[
new Date(2015,8,3),
3.96
],
[
new Date(2015,8,4),
3.96
],
[
new Date(2015,8,7),
4.1
],
[
new Date(2015,8,8),
3.98
],
[
new Date(2015,8,9),
3.96
],
[
new Date(2015,8,10),
3.9
],
[
new Date(2015,8,11),
4
],
[
new Date(2015,8,14),
4.1
],
[
new Date(2015,8,15),
4.32
],
[
new Date(2015,8,16),
4.42
],
[
new Date(2015,8,17),
4.42
],
[
new Date(2015,8,18),
4.34
],
[
new Date(2015,8,21),
4.34
],
[
new Date(2015,8,22),
4.38
],
[
new Date(2015,8,23),
4.22
],
[
new Date(2015,8,24),
3.8
],
[
new Date(2015,8,25),
3.8
],
[
new Date(2015,8,28),
2.92
],
[
new Date(2015,8,29),
2.92
],
[
new Date(2015,8,30),
2.88
],
[
new Date(2015,9,1),
3.72
],
[
new Date(2015,9,2),
3.7
],
[
new Date(2015,9,5),
3.58
],
[
new Date(2015,9,6),
3.32
],
[
new Date(2015,9,7),
3.32
],
[
new Date(2015,9,8),
3.12
],
[
new Date(2015,9,9),
3.1
],
[
new Date(2015,9,12),
3.14
],
[
new Date(2015,9,13),
3.36
],
[
new Date(2015,9,14),
3.36
],
[
new Date(2015,9,15),
3.44
],
[
new Date(2015,9,16),
3.36
],
[
new Date(2015,9,19),
3.28
],
[
new Date(2015,9,20),
3.04
],
[
new Date(2015,9,21),
2.88
],
[
new Date(2015,9,22),
2.46
],
[
new Date(2015,9,23),
2.46
],
[
new Date(2015,9,26),
2.3
],
[
new Date(2015,9,27),
2.18
],
[
new Date(2015,9,28),
1.9
],
[
new Date(2015,9,29),
1.62
],
[
new Date(2015,9,30),
1.62
],
[
new Date(2015,10,2),
2.26
],
[
new Date(2015,10,3),
2.26
],
[
new Date(2015,10,4),
2.12
],
[
new Date(2015,10,5),
2.02
],
[
new Date(2015,10,6),
1.98
],
[
new Date(2015,10,9),
2.36
],
[
new Date(2015,10,10),
2.34
],
[
new Date(2015,10,11),
2.26
],
[
new Date(2015,10,12),
2.18
],
[
new Date(2015,10,13),
2.14
],
[
new Date(2015,10,16),
2.32
],
[
new Date(2015,10,17),
2.32
],
[
new Date(2015,10,18),
2.32
],
[
new Date(2015,10,19),
2.32
],
[
new Date(2015,10,20),
2.28
],
[
new Date(2015,10,23),
2.34
],
[
new Date(2015,10,24),
2.52
],
[
new Date(2015,10,25),
2.86
],
[
new Date(2015,10,26),
3.14
],
[
new Date(2015,10,27),
3.14
],
[
new Date(2015,10,30),
3.7
],
[
new Date(2015,11,1),
3.96
],
[
new Date(2015,11,2),
3.96
],
[
new Date(2015,11,3),
4.06
],
[
new Date(2015,11,4),
4.5
],
[
new Date(2015,11,7),
4.76
],
[
new Date(2015,11,8),
4.8
],
[
new Date(2015,11,9),
4.84
],
[
new Date(2015,11,10),
4.84
],
[
new Date(2015,11,11),
4.84
],
[
new Date(2015,11,14),
4.84
],
[
new Date(2015,11,15),
4.84
],
[
new Date(2015,11,16),
4.9
],
[
new Date(2015,11,17),
4.92
],
[
new Date(2015,11,18),
4.92
],
[
new Date(2015,11,21),
4.92
],
[
new Date(2015,11,22),
4.96
],
[
new Date(2015,11,23),
4.96
],
[
new Date(2015,11,24),
4.96
],
[
new Date(2015,11,25),
4.96
],
[
new Date(2015,11,28),
4.88
],
[
new Date(2015,11,29),
4.88
],
[
new Date(2015,11,30),
5.12
],
[
new Date(2015,11,31),
5.18
],
[
new Date(2016,0,4),
5.12
],
[
new Date(2016,0,5),
5.1
],
[
new Date(2016,0,6),
5.08
],
[
new Date(2016,0,7),
5.18
],
[
new Date(2016,0,8),
5.12
],
[
new Date(2016,0,11),
5.14
],
[
new Date(2016,0,12),
5.08
],
[
new Date(2016,0,13),
5
],
[
new Date(2016,0,14),
5.1
],
[
new Date(2016,0,15),
4.98
],
[
new Date(2016,0,18),
4.98
],
[
new Date(2016,0,19),
4.98
],
[
new Date(2016,0,20),
4.98
],
[
new Date(2016,0,21),
4.98
],
[
new Date(2016,0,22),
4.98
],
[
new Date(2016,0,25),
5.02
],
[
new Date(2016,0,26),
5.2
],
[
new Date(2016,0,27),
5.22
],
[
new Date(2016,0,28),
5.26
],
[
new Date(2016,0,29),
5.34
],
[
new Date(2016,1,1),
5.44
],
[
new Date(2016,1,2),
5.44
],
[
new Date(2016,1,3),
5.44
],
[
new Date(2016,1,4),
5.44
],
[
new Date(2016,1,5),
5.44
],
[
new Date(2016,1,15),
5.44
],
[
new Date(2016,1,16),
4.78
],
[
new Date(2016,1,17),
3.84
],
[
new Date(2016,1,18),
2.74
],
[
new Date(2016,1,19),
2.38
],
[
new Date(2016,1,22),
2.16
],
[
new Date(2016,1,23),
2.14
],
[
new Date(2016,1,24),
1.86
],
[
new Date(2016,1,25),
1.86
],
[
new Date(2016,1,26),
1.9
],
[
new Date(2016,1,29),
1.96
],
[
new Date(2016,2,1),
2.58
],
[
new Date(2016,2,2),
2.76
],
[
new Date(2016,2,3),
3.4
],
[
new Date(2016,2,4),
4.14
],
[
new Date(2016,2,7),
4.5
],
[
new Date(2016,2,8),
4.7
],
[
new Date(2016,2,9),
4.82
],
[
new Date(2016,2,10),
4.56
],
[
new Date(2016,2,11),
4.4
],
[
new Date(2016,2,14),
4.36
],
[
new Date(2016,2,15),
4.36
],
[
new Date(2016,2,16),
4.28
],
[
new Date(2016,2,17),
4.04
],
[
new Date(2016,2,18),
3.9
],
[
new Date(2016,2,21),
3.84
],
[
new Date(2016,2,22),
3.72
],
[
new Date(2016,2,23),
3.72
],
[
new Date(2016,2,24),
3.48
],
[
new Date(2016,2,25),
3.4
],
[
new Date(2016,2,28),
3.36
],
[
new Date(2016,2,29),
3.42
],
[
new Date(2016,2,30),
3.66
],
[
new Date(2016,2,31),
4.06
],
[
new Date(2016,3,1),
4.38
],
[
new Date(2016,3,4),
4.54
],
[
new Date(2016,3,5),
4.56
],
[
new Date(2016,3,6),
4.78
],
[
new Date(2016,3,7),
4.8
],
[
new Date(2016,3,8),
4.85
],
[
new Date(2016,3,11),
4.9
],
[
new Date(2016,3,12),
4.94
],
[
new Date(2016,3,13),
4.94
],
[
new Date(2016,3,14),
4.94
],
[
new Date(2016,3,15),
4.94
],
[
new Date(2016,3,19),
4.94
],
[
new Date(2016,3,20),
4.94
],
[
new Date(2016,3,21),
4.94
],
[
new Date(2016,3,22),
4.94
],
[
new Date(2016,3,25),
4.54
],
[
new Date(2016,3,26),
4.12
],
[
new Date(2016,3,27),
3.58
],
[
new Date(2016,3,28),
3.8
],
[
new Date(2016,3,29),
3.82
],
[
new Date(2016,4,4),
4.44
],
[
new Date(2016,4,5),
4.5
],
[
new Date(2016,4,6),
4.32
],
[
new Date(2016,4,9),
3.86
],
[
new Date(2016,4,10),
3.64
],
[
new Date(2016,4,11),
3
],
[
new Date(2016,4,12),
2.92
],
[
new Date(2016,4,13),
2.56
],
[
new Date(2016,4,16),
2.78
],
[
new Date(2016,4,17),
2.55
],
[
new Date(2016,4,18),
1.85
],
[
new Date(2016,4,19),
1.17
],
[
new Date(2016,4,20),
1
],
[
new Date(2016,4,23),
0.93
],
[
new Date(2016,4,24),
0.93
],
[
new Date(2016,4,25),
0.85
],
[
new Date(2016,4,26),
0.8
],
[
new Date(2016,4,27),
0.74
],
[
new Date(2016,4,30),
0.6
],
[
new Date(2016,4,31),
0.7
],
[
new Date(2016,5,1),
1.94
],
[
new Date(2016,5,2),
2.18
],
[
new Date(2016,5,3),
2.28
],
[
new Date(2016,5,6),
2.2
],
[
new Date(2016,5,7),
2.04
],
[
new Date(2016,5,8),
1.88
],
[
new Date(2016,5,9),
1.4
],
[
new Date(2016,5,10),
1.65
],
[
new Date(2016,5,13),
1.62
],
[
new Date(2016,5,14),
1.56
],
[
new Date(2016,5,15),
1.62
],
[
new Date(2016,5,16),
1.18
],
[
new Date(2016,5,17),
1.18
],
[
new Date(2016,5,20),
1.32
],
[
new Date(2016,5,21),
1.1
],
[
new Date(2016,5,22),
1.1
],
[
new Date(2016,5,23),
1.1
],
[
new Date(2016,5,24),
1.06
],
[
new Date(2016,5,27),
1.63
],
[
new Date(2016,5,28),
1.63
],
[
new Date(2016,5,29),
1.63
],
[
new Date(2016,5,30),
1.63
],
[
new Date(2016,6,1),
1.64
],
[
new Date(2016,6,4),
1.61
],
[
new Date(2016,6,5),
1.57
],
[
new Date(2016,6,6),
1.47
],
[
new Date(2016,6,7),
1.36
],
[
new Date(2016,6,8),
1.27
],
[
new Date(2016,6,11),
1.12
],
[
new Date(2016,6,12),
1.14
],
[
new Date(2016,6,13),
1.14
],
[
new Date(2016,6,14),
1.1
],
[
new Date(2016,6,15),
1.2
],
[
new Date(2016,6,18),
1.25
],
[
new Date(2016,6,19),
1.25
],
[
new Date(2016,6,20),
1.25
],
[
new Date(2016,6,21),
1.25
],
[
new Date(2016,6,22),
1.25
],
[
new Date(2016,6,25),
1.4
],
[
new Date(2016,6,26),
1.4
],
[
new Date(2016,6,27),
1.35
],
[
new Date(2016,6,28),
1.35
],
[
new Date(2016,6,29),
1.4
],
[
new Date(2016,7,1),
1.6
],
[
new Date(2016,7,2),
1.5
],
[
new Date(2016,7,3),
1.5
],
[
new Date(2016,7,4),
1.4
],
[
new Date(2016,7,5),
1.3
],
[
new Date(2016,7,8),
1.28
],
[
new Date(2016,7,9),
1.28
],
[
new Date(2016,7,10),
1.28
],
[
new Date(2016,7,11),
1.28
],
[
new Date(2016,7,12),
1.15
],
[
new Date(2016,7,15),
1.15
],
[
new Date(2016,7,16),
1.13
],
[
new Date(2016,7,17),
1.1
],
[
new Date(2016,7,18),
1.03
],
[
new Date(2016,7,19),
0.8
],
[
new Date(2016,7,22),
0.7
],
[
new Date(2016,7,23),
0.6
],
[
new Date(2016,7,24),
0.6
],
[
new Date(2016,7,25),
0.5
],
[
new Date(2016,7,26),
0.5
],
[
new Date(2016,7,29),
0.5
],
[
new Date(2016,7,30),
0.5
],
[
new Date(2016,7,31),
0.5
],
[
new Date(2016,8,1),
0.63
],
[
new Date(2016,8,5),
0.73
],
[
new Date(2016,8,6),
0.7
],
[
new Date(2016,8,7),
0.6
],
[
new Date(2016,8,8),
0.53
],
[
new Date(2016,8,9),
0.53
],
[
new Date(2016,8,12),
0.55
],
[
new Date(2016,8,13),
0.55
],
[
new Date(2016,8,14),
0.55
],
[
new Date(2016,8,15),
0.525
],
[
new Date(2016,8,16),
0.525
],
[
new Date(2016,8,19),
0.45
],
[
new Date(2016,8,20),
0.4
],
[
new Date(2016,8,21),
0.4
],
[
new Date(2016,8,22),
0.4
],
[
new Date(2016,8,23),
0.4
],
[
new Date(2016,8,26),
0.4
],
[
new Date(2016,8,27),
0.4
],
[
new Date(2016,8,28),
0.4
],
[
new Date(2016,8,29),
0.55
],
[
new Date(2016,8,30),
0.675
] 
];
data.addColumn('date','Date');
data.addColumn('number','Overnight');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartAnnotationChartIDb2c7b5c753d() {
var data = gvisDataAnnotationChartIDb2c7b5c753d();
var options = {};
options["width"] = 500;
options["height"] = 300;

    var chart = new google.visualization.AnnotationChart(
    document.getElementById('AnnotationChartIDb2c7b5c753d')
    );
    chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
var pkgs = window.__gvisPackages = window.__gvisPackages || [];
var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
var chartid = "annotationchart";
  
// Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
var i, newPackage = true;
for (i = 0; newPackage && i < pkgs.length; i++) {
if (pkgs[i] === chartid)
newPackage = false;
}
if (newPackage)
  pkgs.push(chartid);
  
// Add the drawChart function to the global list of callbacks
callbacks.push(drawChartAnnotationChartIDb2c7b5c753d);
})();
function displayChartAnnotationChartIDb2c7b5c753d() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  window.clearTimeout(window.__gvisLoad);
  // The timeout is set to 100 because otherwise the container div we are
  // targeting might not be part of the document yet
  window.__gvisLoad = setTimeout(function() {
  var pkgCount = pkgs.length;
  google.load("visualization", "1", { packages:pkgs, callback: function() {
  if (pkgCount != pkgs.length) {
  // Race condition where another setTimeout call snuck in after us; if
  // that call added a package, we must not shift its callback
  return;
}
while (callbacks.length > 0)
callbacks.shift()();
} });
}, 100);
}
 
// jsFooter
</script>
 
<!-- jsChart -->  
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartAnnotationChartIDb2c7b5c753d"></script>
 
<!-- divChart -->
  
<div id="AnnotationChartIDb2c7b5c753d" 
  style="width: 500; height: 300;">
</div>

<br/>

* Chịu tác động của cung, cầu ngắn hạn trên thị trường
* Biến động lớn trong ngắn hạn
* Khó dự báo bằng các yếu tố vĩ mô


---

## Mô hình kinh tế lượng áp dụng đối với xu hướng dài hạn của lãi suất

- Mô hình dự báo chuỗi thời gian sẽ giúp dự báo các giá trị tương lai về một đối tượng dự báo nào đó trên nền tảng xu hướng vận động của chính chuỗi dữ liệu đó trong quá khứ và hiện tại.

- Ngoài ra, các biến kinh tế thường có các mối quan hệ với nhau, và dựa trên các mối quan hệ đó mà chúng ta có thể suy luận được hành vi của một biến số nào đó khi đã có thông tin từ các biến số khác có liên quan.

- Loại mô hình thường được sử dụng để dự báo các biến số kinh tế:
  + Mô hình hồi quy vector (VAR)
  + Mô hình hồi quy sai số vector (VECM)



--- .segue bg:black

## Xây dựng mô hình

---

## Lựa chọn mô hình theo lý thuyết kinh tế

- Mô hình dự báo dựa trên Mô hình lạm phát đối với các quốc gia nhỏ (Inflation Dynamics and Monetary transmission in Vietnam and Emerging Asia) do IMF nghiên cứu và xuất bản năm 2013.

$\Delta p_{t} = \kappa_{1}\Delta\epsilon_{t} + \kappa_{2}\Delta_p{t}^W + \kappa_{3}\Delta M_{t} + \kappa_{4}\Delta Y_{t} + \kappa_{5}\Delta r_{t} + \zeta_{t}$

- Trong đó:
  + $p$: Chỉ số giá tiêu dùng
  + $\epsilon$ : Tỷ giá danh nghĩa
  + $p^W$ : Giá hàng hóa thế giới
  + $M$ : Cung tiền
  + $Y$ : GDP
  + $r$ : Lãi suất danh nghĩa

- Tồn tại sự tác động qua lại của các yếu tố vĩ mô nên mô hình trên có thể được dùng để phân tích và dự báo lãi suất, tỷ giá và tăng trưởng kinh tế.


---

## Nguồn dữ liệu

- Dữ liệu theo quý từ 2000 Q1-2016 Q3, bao gồm các biến:
  + GDP
  + Chỉ số giá tiêu dùng CPI
  + Tín dụng đối với nền kinh tế (sử dụng thay thế cung tiền)
  + Lãi suất tiền gửi và lãi suất cho vay thị trường 1
  + Tỷ giá danh nghĩa đa phương (NEER)
  + Giá dầu giao ngay thế giới, đại diện cho biến giá hàng hóa thế giới

- Nguồn dữ liệu: Quỹ tiền tệ quốc tế, Tổng cục thống kê . Dữ liệu GDP giai đoạn 2000-2012 có năm gốc là 1994 được chuyển sang năm gốc 2010 dựa trên số liệu tăng trưởng GDP trong quá khứ.

- Tỷ giá danh nghĩa đa phương (NEER): dựa trên bình quân hình học, tỷ trọng của các đồng tiền bằng tỷ lệ giao dịch thương mại của Việt Nam với 8 quốc gia (Mỹ, EU, Trung Quốc, Nhật Bản, Hàn Quốc, Thái Lan, Singapore, Đài Loan).


---

## Đặc điểm dữ liệu

<h3>Tính dừng (stationary)</h3>

</div>
- Kiểm định tính dừng(stationary) của chuỗi dữ liệu bằng Augmented Dickey-Fuller test:
<a href="#demo" class="btn btn-info" data-toggle="collapse">Explain</a>
<div id="demo" class="collapse">
<p class="small">Để dự báo chính xác, chuỗi thời gian phải có tính dừng. Một chuỗi thời gian là dừng nếu trung bình, phương sai và tự đồng phương sai (tại các độ trễ khác nhau) sẽ giữ nguyên không đổi dù cho chúng được xác định vào thời điểm nào đi nữa.</p>
</div>



|   Variable    |   ADF   | p-value |
|:-------------:|:-------:|:-------:|
|      GDP      | -0.7562 | 0.9608  |
|      CPI      | -1.9737 | 0.5858  |
|    Credit     | -0.6351 | 0.9713  |
| Deposit_rate  | -1.1042 | 0.9149  |
| Lending_rate  | -0.8989 | 0.9470  |
| Exchange_rate | -1.2675 | 0.8724  |
|      oil      | -0.6559 | 0.9695  |

- Các chuỗi dữ liệu khi kiểm định đều có p-value lớn hơn 0.01(tương ứng với độ tin cậy 99%), do ta không thể bác bỏ giả thuyết __H0: chuỗi dữ liệu không có tính dừng.__


---

## Đặc điểm dữ liệu

<h3>Tính đồng liên kết (cointegration)</h3>

</div>
- Kiểm định tính đồng liên kết trong chuỗi dữ liệu bằng Johansen test:
<a href="#demo1" class="btn btn-info" data-toggle="collapse">Explain</a>
<div id="demo1" class="collapse">
<p class="small">Theo nghiên cứu nổi tiếng của Engle và Granger (1986), khi xét mô hình có nhiều biến số theo chuỗi thời gian, cũng có nhiều trường hợp, mặc dù các biến số là không dừng, nhưng khi thực hiện phép hồi quy hay tổ hợp tuyến tính của các biến này vẫn cho ra một chuỗi dừng. Trong trường hợp này, mô hình vẫn có thể ước lượng được mà không bị hiện tượng hồi quy giả mạo và mối quan hệ giữa các biến được gọi là quan hệ đồng liên kết.</p>
</div>


|              |  test  | 10pct  |  5pct  |  1pct  |
|:-------------|:------:|:------:|:------:|:------:|
|r <= 6 &#124; | 10.23  | 10.49  | 12.25  | 16.26  |
|r <= 5 &#124; | 32.20  | 22.76  | 25.32  | 30.45  |
|r <= 4 &#124; | 56.05  | 39.06  | 42.44  | 48.45  |
|r <= 3 &#124; | 83.86  | 59.14  | 62.99  | 70.05  |
|r <= 2 &#124; | 128.07 | 83.20  | 87.31  | 96.58  |
|r <= 1 &#124; | 186.17 | 110.42 | 114.90 | 124.75 |
|r = 0  &#124; | 276.41 | 141.01 | 146.76 | 158.49 |

- Kết quả trace test lớn hơn giá trị tương ứng với độ tin cậy 99%(1pct) sẽ cho phép bác bỏ giả thuyết H0 (bậc đồng liên kết nhỏ hơn k). Kết quả cho thấy xác suất đến 99% có 5 cặp chuỗi dữ liệu có tính đồng liên kết. Tuy nhiên, để giảm rủi ro chuỗi dữ liệu ngắn sẽ trả ra kết quả không chính xác, ta nên chọn bậc đồng liên kết có giá trị lớn, r=2.

---

## Ước lượng mô hình

- Mô hình ước lượng nhiều chuỗi dữ liệu là không dừng và đồng liên kết. Như vậy, mô hình VECM là phù hợp khi chúng ta có nhiều chuỗi thời gian khác nhau và cần phải xem xét mối quan hệ, tác động qua lại giữa chúng.

- Mô hình được ước lượng bằng phương pháp OLS với bậc đồng liên kết bằng 2. Kết quả ước lượng bao gồm 7 phương trình tương đương với 7 biến số kinh tế.



<a href="Macromodel.html">Original paper</a>

---

## Kiểm định kết quả

### Kiểm định phương sai thay đổi - Heteroskedasticity test


```

	ARCH (multivariate)

data:  Residuals of VAR object vecm.level
Chi-squared = 1624, df = 3920, p-value = 1
```

Mô hình có thể tin tưởng được nếu kết quả cho thấy p-value &gt; 0.01 (xác suất 99%). Phương sai của phần dư không thay đổi.

--- .bigger

## Kiểm định kết quả

<h3>Kiểm định phân bố chuẩn - Normality test</h3>


```

	JB-Test (multivariate)

data:  Residuals of VAR object vecm.level
Chi-squared = 26.962, df = 14, p-value = 0.01947
```

Mô hình có thể tin tưởng được nếu kết quả cho thấy p-value > 0.01 (xác suất 99%). JB test có kết quả p-value > 0.01. Do đó, ta chưa thể bác bỏ giả thuyết __H0:chuỗi phần dư có phân phối chuẩn.__

--- .bigger

## Kiểm định kết quả

<h3>Kiểm định tương quan chuỗi - Serial Correlation test</h3>


```

	Portmanteau Test (asymptotic)

data:  Residuals of VAR object vecm.level
Chi-squared = 815.05, df = 791, p-value = 0.2692
```

Kết quả p-value lớn hơn 0.01, do đó chưa có đủ cơ sở để bác bỏ giả thuyết __H0: Không có tương quan giữa các chuỗi phần dư.__

---

## Kiểm định khả năng dự báo

Khả năng dự báo của mô hình được kiểm định bằng 3 hệ số Trung bình sai số tuyệt đối (RMSE), Trung bình sai số tuyệt đối bình phương (MAE) và Phần trăm sai số tuyệt đối bình quân (MAPE),hệ số càng nhỏ, khả năng dự báo càng chính xác

Mô hình đưa ra dự báo đối với 4 quý tiếp (2015Q4-2016Q3) theo dựa trên dữ liệu từ 2000Q1-2015Q3, kết quả đo lường sai số như sau:


|Indicators |     GDP|  CPI|    Credit| Deposit_rate| Lending_rate| Exchange_rate|   oil|
|:----------|-------:|----:|---------:|------------:|------------:|-------------:|-----:|
|RMSE       | 3057.20| 3.37| 212070.33|         0.82|         0.81|          4.80|  6.55|
|MAE        | 2842.39| 2.83| 205176.83|         0.75|         0.73|          4.59|  6.20|
|MAPE       |    0.38| 1.90|      3.63|        15.11|        10.53|          6.54| 15.69|

Có thể thấy sai số đối với dự báo GDP,CPI, tăng trưởng tín dụng và lãi suất cho vay tương đối nhỏ (MAPE<15%) và có thể dùng để dự báo. Giá dầu là biến ngoại sinh, do đó mô hình không thực hiện dự báo đối với mặt hàng này.

---

## Ứng dụng

<h3> Dự báo các chỉ số kinh tế vĩ mô</h3>

Kết quả dự báo 4 quý tiếp theo từ 2016 Q4:


|Indicators           | 2016 Q4| 2017 Q1| 2017 Q2| 2017 Q3|
|:--------------------|-------:|-------:|-------:|-------:|
|GDP (%YoY)           |    7.67|    7.29|    5.85|    7.64|
|Inflation (%YoY)     |    3.71|    3.58|    3.28|    4.28|
|Credit growth (%YoY) |   21.86|   25.56|   29.48|   33.05|
|Lending rate (%)     |    6.09|    5.77|    5.82|    6.03|
|NEER                 |   68.98|   70.42|   71.71|   71.25|


--- &twocol

## Ứng dụng

<h3>Dự báo tác động của chính sách</h3>

Một ứng dụng quan trọng khác của mô hình là khả năng phân tích tác động của chính sách tiền tệ với nền kinh tế nói chung và hoạt động kinh doanh nói riêng thông qua hàm xung ứng.

*** =left

<strong>Huy động -> Cho vay</strong>
<p class="small">Lãi suất huy động có ảnh hưởng cùng chiều tới lãi suất cho vay lớn nhất trong 2 quý đầu tiên, tác động sẽ giảm mạnh kể từ quý thứ 3.</p>


![plot of chunk unnamed-chunk-12](assets/fig/unnamed-chunk-12-1.svg)


*** =right

<strong>Giá dầu -> Lạm phát</strong>
<p class="small">Biến động giá dầu có tác động khá lớn tới lạm phát tại nước ta. Tuy nhiên, tác động có độ trễ khoảng 3 đến 4 quý.</p>

![plot of chunk unnamed-chunk-13](assets/fig/unnamed-chunk-13-1.svg)

---

## Web application

Ứng dụng khai thác kết quả mô hình:

<a href="https://duongtson.shinyapps.io/shiny/" target="_blank">Web application</a> 


--- .segue bg:grey .quote

## THANK YOU FOR LISTENING





