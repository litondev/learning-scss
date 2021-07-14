scss dan sass
untuk mengunakan sass & scss install sass dulu 

npm install -g sass 

di gunakan untuk mencovert scss/sass file ke css
sass --watch file.scss/sass file.css

hati-hati dalam mengunakan '' dan "" di scss dan sass tidak akan berfungsi 
lebih baik di kasih kayak gini
$nama: #777;

untuk perbedaan nya adalah 
scss mengunakan { } dan ;
sedangkan 
sass
tidak mengunakan { } dan ; 

=> ada perbedaan juga kalau pakai mixin di scss dan sass

scss & sass mengunakn $ sebagai variabel

scss & sass sama kayak css hanya saja penambahan fiture yang seperti bahas pemrograman sepert variabel,function,include,class dan lain-lain

#{'nama-variabel'} => sama memangil variabel di tempat tertentu

nastet => 
#id_nama{
	p {
	 color:red
	}
}
sama kayak 
#id_nama p {
	color:red
}

include =>
@use 'base.scss'
#id_nama {
	color: base.$nama_variabel_yang_ada_di_base;
}

mixins => 
@mixin aku_function($paramater){
	color: $parameter;
}

#id_nama{
	@include aku_function(nama_parameter);
}


extend => 
%parent{
 color: red;
}

#id_nama{
 @extend %parent;
 background:red;
}

oprator =>
#lat{
 height: 300px - 200px;
}

function => 
@function aku_function($list){
	@return $new-list;
}

#id_nama{
	color: aku_function(red)
}

if =>
$color: true;

@if $color{
	color:red
}

@if $color{
	color:blue;
}else{
	color:red;
}

for => 
$base-color: #9789;

@for $i from 1 through 3 {
	background-color: $i*5%;
}

each =>
$sizes: 40px,50px,80px;

each $size in $sizes {
	.icon-#{size}{
	 height: $size
	}
}

while =>
@function pink($value,$base,$ration){
@while $value > $base {
	$value: $value/$ratio
}

@return $value
}