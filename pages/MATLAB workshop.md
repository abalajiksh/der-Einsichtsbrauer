- ## Day 1
- ## Day 2
- ```matlab
  %-- 29/06/21, 9:00 AM --% M = eye(3) M = eye(5) M = zeros(3) M = zeros(4) M = ones(10) M = ones(2) M = magic(10) M(24) ind2sub(M(24)) ind2sub(M, 24) sub2ind(M, 24)
  
  A = [1,2,3;4,5,6;7,8,9]
  
  B = magic(3); A/B A\B inv(A) det(B) det(A) norm(A) rank(A) rank(B) clc f(x) = @(x) sin(x) + cos(x) - tan(x) + exp(-x); f = @(x) sin(x) + cos(x) - tan(x) + exp(-x); f2 = @(x,y) sin(x) + cos(y); f(22) f2(23,45) clc car1 = car(25.4, 20, 25); car1 car1.accelerate(5) car1.fuelCapacity car2 = car(45.6, 35, 15); car2.accelerate(3) clc car1 car2
  
  cars = car([25:30],[30:35],[5:10]);
  
  cars = car([25:30],[30:35],[5:10])
  
  cars = car(25:30,30:35,5:10) clc
  
  stud1 = NITC('b170632ep','ashwin','aba@ab.com','C');
  
  stud1.rollNo clc exampleScript
  idx = M < 2;
  
  M = magic(6);
  
  idx = M < 5;
  
  M(idx) = M(idx) -2; M exampleScript M(M<5) = M(M<5) - 2; M = magic(6); M(M<5) = M(M<5) - 2; M clc A B R = chol(B) R = chol(A) A = -1A; R = chol(A)
  
  m = 4;
  
  ii = rand(m);
  
  out = iiii.';
  
  R = chol(out)
  
  L = R'
  
  out LR clc [L,U,P] = lu(A) R = qr(A); R [Q,R] = qr(A) QR RQ clc [U,S,V] = svd(A) eig(A) clc eig(B) sqrt(A) sqrtm(A) ansans clc expm(A) exp(A) logm(A) A = -1A; logm(A) log(A)
  ```
- ## Day 3
- ```matlab
  %-- 30/06/21, 8:02 AM --%
  y = @(x) x.^2 + 3x.^3 + 7;
  y = @(x) x.^2 + 3*x.^3 + 7;
  yIn = inline('x.^2 + 3*x.^3 + 7');
  y(2)
  yIn(2)
  yFun = @humps
  yFun(2)
  clc
  yHad = @myHandleFunc
  myHandleFunc(1,2)
  yHad(1,2)
  clc
  feval(yHad, 1, 2)
  f = inline('sin(x) + x*cos(y)', 'x', 'y')
  f(1,2)
  feval(f,1,2)
  clc
  fplot(@humps,[-5 5])
  fplot(@humps,[-1 3 0 30])
  fplot(@humps,[-1, 3, 0, 30])
  fplot(@humps,[-1, 3, 0, 3])
  clc
  fplot(@humps,[-1, 3; 0, 3])
  clc
  fplot(@humps,[-5 5])
  grid on
  fplot([@humps, y],[-5 5])
  fplot(['@humps', 'y'],[-5 5])
  clc
  f = inline('[y, yFun]')
  f([1;2;3])
  f([1 2 3])
  clc
  fminbnd(@humps, 0.3,1)
  fplot(@humps,[-5 5])
  z = fminsearch(yHad, [-1.2,1])
  clc
  fzero(@humps, -0.2)
  q = quad(@humps,0,1)
  q = quad1(@humps,0,1)
  q = quad(@humps,0,1)
  q = quad(@humps,0,1,@quad1)
  dblquad(yHad,1,2,3,4)
  dblquad(yHad,1,2,3,4, [],@quad1)
  clc
  q = quadl(@humps,0,1)
  q = quad(@humps,0,1)
  dblquad(yHad,1,2,3,4, [],@quadl)
  dblquad(yHad,1,2,3,4)
  clc
  [x,y] = ode45(@myHandleFunc, [1:0.01:10], 0)
  clc
  plot(x,y)
  [x,y] = ode23(@myHandleFunc, [1:0.01:10], 0);
  plot(x,y)
  clc
  y = cumsum(rand(200,5)-0.5);
  plot(y)
  legend('1','2','3','4','5')
  title('random walk')
  clc
  A = randi([1 10], 1,5)
  B = randi([-1 9], 1,5)
  C = intersect(A,B)
  [C, pos] = intersect(A,B)
  D = union(A,B)
  E = setdiff(A,B)
  F = setdiff(B,A)
  a = ismember(A,15)
  a = ismember(B, 3)
  B(B==3)
  B==3
  clc
  fourierTransform
  invFourierTran
  clc
  img = imread('wave.jpg');
  img = imread('wave.jpeg');
  size(img)
  img2 = inv(img)
  img2 = img(:,end:-1:1,:);
  imwrite(img2, 'mirr_wave.jpeg');
  ft = fftshift(fff2(img));
  ft = fftshift(fft2(img));
  imwrite(ft,'ft_wave.jpeg');
  clc
  O = magic(4);
  inv(O)
  inv(O)*O
  eye(4) == inv(O)*O
  clc
  ```
- ## Day 4
- ```matlab
  %-- 01/07/21, 8:53 AM --%
  clc
  %-- 01/07/21, 4:28 PM --%
  syms a b
  simplify(6*a*b + 3*a^2 + 2*a*b)
  simplify(sym(2/5 + 4/7 + 9/17))
  2/5 + 4/7 + 9/17
  syms a b real
  solve(a^2 +1)
  syms a b unreal
  syms a b
  solve(a^2 +1)
  x = sym('x')
  x = sym('x','real')
  x = sym('x')
  A = [1/3,4/5;5/2,6/7]
  sym(A)
  A = sym(A);
  A
  numeric(A)
  isnumeric(A)
  double(A)
  p = [2 3 -7 14 5];
  roots(p)
  p2 = [3 4 -12 6];
  roots(p2)
  poly2sym(p)
  ps = poly2sym(p)
  ps2 = poly2sym(p2)
  ps*ps2
  simplify(ps*ps2)
  poly2sym(p, 'v')
  poly2sym(p, 'a')
  poly2sym(p, a)
  digits(ps)
  digits(2)
  double(A)
  digits(7)
  double(A)
  syms a b c
  solve('a*x^2 + b*x + c',a)
  solve('a*x^2 + b*x + c = 0',a)
  solve('a*x^2 + b*x + c = 0','a')
  clc
  eqn = a*x^2 + b*x + c == 0
  solve(eqn,a)
  solve(eqn,b)
  solve(eqn,c)
  solve(eqn)
  clc
  si = numeric(solve('sin(x) = cos(x)'))
  si = numeric(solve('sin(x) == cos(x)'))
  si = numeric(solve(sin(x) == cos(x)))
  si = double(solve(sin(x) == cos(x)))
  si = (solve(sin(x) == cos(x)))
  maple('f:x->f(x)')
  pm = expand(ps*ps2)
  pf = factor(pm)
  limit(pm, inf)
  limit(pm,12.7)
  diff(pm)
  diff(pm,x,3)
  int(pm,x)
  dsolve(pm,x)
  clc
  syms y
  eqn = diff(y,x) == pm
  dsolve(eqn,x)
  syms y(x)
  eqn = diff(y,x) == pm
  dsolve(eqn,x)
  clc
  syms n
  su = (3+2*n)/((1-n)*n*7^n)
  s1 = symsum(su,n,2,inf)
  double(s1)
  s1 = symsum(su,n,2,5)
  clc
  e^A
  exp(A)
  A
  expm(A)
  double(expm(A))
  double(exp(A))
  clc
  %-- 01/07/21, 7:58 PM --%
  ```
-