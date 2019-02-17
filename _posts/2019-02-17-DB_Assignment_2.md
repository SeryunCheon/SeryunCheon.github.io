---
layout: post
database: true
title:  "DB Assignment 2"
date:   2019-02-17
excerpt: "커미션을 받을수 있는 자격이 되는 사원의 이름, 급여, 커미션을 출력: 
select empName, job, comm from employee where comm is not null and comm<>0;"

tag:
- sample
- test
- blog
comments: false
---
## 데이터베이스 쿼리문 과제 2( 2018' 비트캠프 과정)
- - -

Employee, dept Table이 아래와 같이 주어졌을시,

![emp](https://user-images.githubusercontent.com/30023840/52917024-cb5c2480-3329-11e9-817f-fd787c119a8f.JPG)

1.덧셈 연산자를 이용하여 모든 사원에대해 300원 급여 인상을 계산한후
사원의 이름, 급여, 인상된 급여를 싹 출력
select empName as '사원이름', sal as '원 급여', (sal+300)as '300원 인상된 급여' from employee;


2.사원번호가 7788인 사원의 이름과 부서번호를 출력
select empName, deptno from employee where empNo = 7788;


3.급여가 2000에서 3000사이에 포함되지 않는 사원의 이름과 급여를 출력
select empName, sal from employee where sal not between 2000 and 3000;


4.81년 2월20일부터 81년 5월 1일 사이에 입사한 사원의 이름 담당업무 입사일을 출력
select empName, job, hiredate from employee where hiredate between '1981-02-20' and '1981-05-01';


5.부서번호가 20및 30에 속한 사원의 이름과 부서번호를 출력
select empName, deptno from employee where deptno = 20 or deptno=30;
select empName, deptno from employee where deptno in(20,30);

6.사원의 급여가 2000에서 3000사이에 포함되고 부서번호가 20또는 30인 사원의 이름과 급여부서번호를 출력
select empName, deptno from employee where (sal between 2000 and 3000) and (deptno = 20 or deptno=30);
select empname, deptno from employee where sal between 2000 and 3000 && deptno in(20,30);

7.81년도에 입사한 사원의 이름과 입사일을 출력
select empName,hiredate from employee where hiredate between '1981-00-00' and '1982-00-00';
select empName,hiredate from employee where hiredate like '1981%';


8.관리자가 없는 사원의 이름과 담당업무를 출력
select empName, job from employee where mgr is null;


9.커미션을 받을수 있는 자격이 되는 사원의 이름, 급여, 커미션을 출력
select empName, job, comm from employee where comm is not null and comm<>0;
select empName, job, comm from employee where comm is not null and comm!=0;
select empName, job, comm from employee where comm is not null and comm ^0;


10.세번째 문자가 R인 사원의 이름을 표시
select empName from employee where empname like '__r%';


11.이름에 A와 E를 모두 포함하는 사원의 이름을 표시.
select empName from employee where empname like '%a%e%';


12.담당업무가 사무원(CLERK) 또는 영업맨 이면서 급여가 1600, 950 또는 1300이 아닌 사원의 이름 담당업무 급여를 출력
select empname,job,sal from employee where job in('clerk','salesman') and sal not in (1600,950,1300);


13.커미션이 500이상인 사원의 이름과 급여 커미션을 출력.
select empName, sal, comm from employee where comm >= 500;



