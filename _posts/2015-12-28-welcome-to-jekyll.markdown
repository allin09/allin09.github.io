---
layout: post
title:  "qunit 判断三角形测试用例!"
date:   2015-12-28 20:03:02 +0800
categories: [test, sample]
---

<html>

	<head>
		<meta charset="UTF-8">
		<title>QUnit Test Suite</title>
		<link rel="stylesheet" href="../../../../../css/qunit-1.22.0.css">
		<script src="../../../../../js/qunit-1.22.0.js"></script>
	</head>

	<body>
		<div id="qunit"></div>
		<div id="qunit-fixture"></div>
		<script>
			function Triangle(a, b, c) {
				if (a && b && c && a > 0 && b > 0 && c > 0 && a < (b + c) && b < (a + c) && c < (a + b)) {
					if (!(this instanceof Triangle)) {
						return new Triangle(a, b, c);
					}
					this.a = a;
					this.b = b;
					this.c = c;
					this.s=function(){
						 var p = (this.a+this.b+this.c)/2;
   						return Math.sqrt(p*(p-this.a)*(p-this.b)*(p-this.c));
					}
					return true;
				}
				return false;
			}
			Triangle.prototype.zj=function(){
				return !!((this.a==this.b&&this.a!=this.c)||(this.a==this.c&&this.a!=this.b))
			}
			Triangle.prototype.qd=function(){
				return !!(this.a==this.b&&this.a==this.c)
			}
			QUnit.test("测试是否为三角形", function(assert) {
				assert.equal(Math.sqrt(8)*Math.sqrt(8),8,"Math.sqrt(8)");
				assert.equal(Math.ceil(Triangle(Math.sqrt(8),2,2).s()),2,"面积为2");
				assert.ok(Triangle("1",1,1), "是三角形");
				assert.ok(Triangle(Math.sqrt(8),2,2), "是三角形");
				
			});
			QUnit.test("测试三角形类型", function(assert) {
				assert.ok(Triangle("1",1,1).zj(), "直角三角形");
				assert.ok(Triangle("1",1,1).qd(), "全等三角形");
				assert.ok(Triangle(Math.sqrt(8),2,2).zj(), "直角三角形");
				assert.ok(Triangle(Math.sqrt(8),2,2).qd(), "全等三角形");
			});
		</script>
	</body>

</html>
