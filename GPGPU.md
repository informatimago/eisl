manual of GPGPU functions

accuracy(arg1, ls)

accuracy(mt1,ls)
return accuracy rate as float number. mt1 is set of row-vector.Each row-vector is onehot. ls is list each element is label integer number.
activate(arg1, arg2)

activate(mt,fun) 
apply fun to mt. fun is :sigmoid, :tanh, :relu :softmax
adagrad(arg1, arg2, arg3, lr)

adagrad(weight,h,grad,lr) 
adagrad optimizer return tuple(h,w) for learn/3 in DeepPipe2
adam(arg1, arg2, arg3, arg4, lr)

adam(w,m,v,grad,lr) 
adam optimizer return tuple(m1,v1,w1) for learn/3 in DeepPipe2
add(arg1, arg2)

add(mt1,mt2) 
generate matrix mt1+mt2. if mt1 or mt2 is row vector, expand size to matrix. This function is for bias add in DL.

add_diff(arg, x, y, val)
add_diff(mt,r,c,val) elt(mt,x,y) := elt(mt,x,y + val.
add_diff(arg, n1, c1, h1, w1, val)

analizer(arg, id)
analizer(mt,id)
analizer(ts,id) display id-number,max-element,min-element,average. for debug.
average(arg)

average(mt) 
caluculate average of row-vector and generate row-vector that each element is average. For Deep-Learning.
convolute(arg1, arg2, st_h, st_w, pad)

convolute(ts1,ts2,st_h,st_w,pad) 
convolution with input-tensor(ts1), filter-tensor(ts2), stride(st_h,st_w), padding(pad)
correct(arg1, ls)

correct(mt1,ls) 
return correct number as integer number. mt1 is set of row-vector.Each row-vector is onehot. ls is list each element is label integer number.

deconvolute(arg1, arg2, st_h, st_w, pad)
deconvolute(ts1,ts2,st_h,st_w,pad) 
deconvolution with input-tensor(ts1), filter-tensor(ts2), stride(st_h,st_w), padding(pad) 1st arg loss-tensor 2nd arg filter-tesnor

diff(a, b, c)
diff(mt1,mt2,fun)
for each element multiply differntial of mt2 and mt1. fun is :sigmoid :tanh, :relu.

dropout(arg, dr)
generate mask matrix or tensor for dropout


emult(mt1,mt2)
generate Hadamard matrix.

full(arg)
full(ts) transfer from 4 DIM tensor to matrix.
gradfilter(arg1, arg2, arg3, st_h, st_w, pad)

gradfilter(ts1,ts2,ts3,st_h,st_w,pad) 
gradient by backpropagation. ts1 is input-tesor, ts2 is filter-tensor, ts3 is loss-tensor, st_h and st_w are stride size, pad is padding size. calculate gradient of filter.
ident(r)

ident(n) 
generate ident matrix of size n.


loss(arg1, arg2, atom)
generate float that is average of loss. fun is :square or :cross. :square means mean_square function, and :cross means cross_entropy function. mt1 is calculated data matrix , mt2 is train data matrix. each data is row vector.


momentum(mt1,mt2,mt3,lr) 
for each element v = 0.5 mt2(x,y) - lr mt3(x,y). w = mt1 + v. return tuple {v,w} for learn/3 in DeepPipe2

mult(s, s)
generate matrix mt1mt2 with cuBLAS. if mt1 or mt2 is float number. generate matrix that each element is selt(x,y)

pooling(arg, st_h, st_w)
pooling(tensor,st_h,st_w) pooling with stride st_w st_w. size of H and W must be less 1000. max 999*999. return tuple {tensor-for-forward,tensor-for-backward}


random_select(mt1,mt2,n) 
select same row data from matrix(mt1) and matrix(mt2)
reshape(x, i)


rms(arg1, arg2, arg3, lr)
rms(weight,h,grad,lr) RMSprop optimizer return tuple(h,w) for learn/3 in DeepPipe2

sgd(arg1, arg2, lr)
sgd(mt1,mt2,lr,dr) element of mt1 - element of mt2*lr. and dropout with rate dr.
sgd(_, _, _, _)


normalizer(ts) 
calculate average of nth data and sub each elemet the average. when matrix , nothing to do

sub(mt1,mt2) 
generate matrix mt1-mt2. It is possible to adapt tensor

sum(mt) 
return sum of elements
to_list(arg)

trace(mt) return float number. It is trace of matrix.
transpose(arg)

transpose(mt) 
generate transposed matrix

unfull(arg, c, h, w)
unfull(mt,h,w) transfer from matrix to 4 DIM tensor. tensor(N,C,H,W). N is row size of matrix. C is 1.

unpooling(arg1, arg2, st_h, st_w)
unpooing(ts1,ts2,st_h,st_w) 
unpooling with stride st. ts1 is sparse tensor that save index of max element. ts2 is loss tensor.