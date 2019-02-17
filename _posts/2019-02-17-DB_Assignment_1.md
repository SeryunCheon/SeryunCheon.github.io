---
layout: post
database: true
title:  "DB Assignment 1"
date:   2019-02-17
excerpt: "select e1.empname as 사원이름, e1.empno as 사원번호, e2.empname as 관리자이름, e1.mgr as 관리자번호 from employee e1, employee e2 where e1.mgr = e2.empno;"

tag:
- sample
- test
- blog
comments: false
---
## 데이터베이스 쿼리문 과제 1( 2018' 비트캠프 과정)
- - -

Employee, dept Table이 아래와 같이 주어졌을시,

![emp](https://user-images.githubusercontent.com/30023840/52917024-cb5c2480-3329-11e9-817f-fd787c119a8f.JPG)

1. 사원이름과 그 사원이 소속된 부서이름과 지역명 출력

2. 10번 부서에서 담당하는 모든 업무와 지역명 출력(=업무는 JOB)

3. 커미션을 받는 모든사원의 이름, 부서이름, 지역명 출력

4. 사원의 이름 및 사원번호를 관리자이름 및 관리자번호와 함께출력

6. WARD보다 늦게 입사한 사원의 이름과 입사일을 출력

7. 관리자보다 먼저 입사한 모든 사원의 이름, 입사일, 부서이름을 관리자의 이름 및 입사일과 함께 출력.


<details>
<summary>정답(은 따로 없지만서도 제가 작성한 코드를 보고싶다면 클릭!)</summary>
<div>

1.<br>
select e.empname, d.dname, d.dloc from employee e, dept d where e.deptno=d.deptno;<br>
select empname,dname,dloc from employee, dept where employee.deptno=dept.deptno;<br>


2.<br>
select e.job, d.dloc from employee e, dept d where e.deptno=d.deptno && e.deptno=10;<br>
select e.job, d.dloc from employee e join dept d using(deptno) where deptno=10;<br>
select a.job, b.dloc from employee a join dept b using (deptno) where a.deptno = 10;<br>
 select e.job as '10번 부서에서 담당하는 모든업무', d.dloc as '지역명' from employee e, dept d where e.deptno =10 && d.deptno = 10;<br>



3.<br>
select e.empname as , d.dname as, d.dloc from employee e, dept d where e.deptno = d.deptno && comm is not null && comm <> 0;<br>

select e.empname, d.dname,d.dloc from employee e join dept d using(deptno) where comm in not null && comm not in(0);<br>

select empname, dname, dloc from employee e join dept d using (deptno) where comm not in (0);<br>

select a.empname, b.dname, b.dlocfrom employee a inner join dept b on a.deptno = b.deptno where a.comm is not null;<br>


4.<br>
select e1.empname as 사원이름, e1.empno as 사원번호, e2.empname as 관리자이름, e1.mgr as 관리자번호 from employee e1, employee e2 where e1.mgr = e2.empno;<br>
select a.empname, a.empno, b.empname as manager, a.mgr from employee a join employee b on a.mgr = b.empno;<br>


6.<br>
select empname as 'ward보다 늦게 입사한 사원들', hiredate as '입사일' 
from employee where hiredate >'1981-02-22';<br>

select empname, hiredate
from employee where hiredate > (select hiredate from employee where empname = 'WARD' ) ;<br>


select e2.ename, e2.hiredate from employee e1, employee e2 where (e1.ename like 'ward') and (e2.hiredate > e1.hiredate);<br>

7.<br>
select e1.empname, e1.empno, e1.hiredate, d.dname, e2.empname as manager, e2.hiredate as manager_hiredate from employee e1, dept d, employee e2 where e1.mgr = e2.empno && e1.hiredate < e2.hiredate && e1.deptno=d.deptno; <br>

select a.empname, a.empno, a.hiredate, c.dname, b.empname as manager, b.hiredate as manager_hiredate from employee a join employee b on a.mgr = b.empno join dept c on a.deptno = c.deptno where a.hiredate < b.hiredate; <br>

</div>
</details>



