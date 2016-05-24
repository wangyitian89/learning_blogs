## PHP数组排序  

> 摘录自php_manual手册

PHP 有一些用来排序数组的函数， 这个文档会把它们列出来。     

主要区别有：     

1. 有些函数基于 array  的键来排序， 而其他的基于值来排序的：$array['key'] = 'value';。     
2. 排序之后键和值之间的关联关系是否能够保持， 是指排序之后数组的键可能 会被重置为数字型的（0,1,2 ...）。     
3. 排序的顺序有：字母表顺序， 由低到高（升序）， 由高到低（降序），数字排序，自然排序，随机顺序或者用户自定义排序。     
4. 注意：下列的所有排序函数都是直接作用于数组本身， 而不是返回一个新的有序的数组。     
5. 以下函数对于数组中相等的元素，它们在排序后的顺序是未定义的。 （也即相等元素之间的顺序是不稳定的）。     

**排序函数属性**    



|	函数名称	|排序依据	|数组索引键保持|排序的顺序	|相关函数|
|---|---|---|---|---|
|	array_multisort()	|值	|键值关联的保持，数字类型的不保持	|第一个数组或者由选项指定	|array_walk()		|
|	asort()				|值	|是		|由低到高			|arsort()			|
|	arsort()			|值	|是		|由高到低			|asort()			|
|	krsort()			|键	|是		|由高到低			|ksort()			|
|	ksort()				|键	|是		|由低到高			|asort()			|
|	natcasesort()		|值	|是		|自然排序，大小写不敏感|natsort()			|
|	natsort()			|值	|是		|自然排序			|natcasesort()		|
|	rsort()				|值	|否		|由高到低			|sort()				|
|	shuffle()			|值	|否		|随机				|array_rand()		|
|	sort()				|值	|否		|由低到高			|rsort()			|
|	uasort()			|值	|是		|由用户定义			|uksort()			|
|	uksort()			|键	|是		|由用户定义			|uasort()			|
|	usort()				|值	|否		|由用户定义			|uasort()			|

以其中一个函数为例：    

    bool sort  ( array &$array  [, int $sort_flags  = SORT_REGULAR  ] )    

**参数**    

1. **array**     
	要排序的数组。     
1. **sort_flags**     
	可选的第二个参数 sort_flags 可以用以下值改变排序的行为：       
	
	排序类型标记：        

	1. SORT_REGULAR  - 正常比较单元（不改变类型）      
	1. **SORT_NUMERIC**  - 单元被作为数字来比较      
	1. **SORT_STRING**  - 单元被作为字符串来比较      
	1. SORT_LOCALE_STRING  - 根据当前的区域（locale）设置来把单元当作字符串比较，可以用 setlocale()  来改变。      
	1. SORT_NATURAL  - 和 natsort()  类似对每个单元以“自然的顺序”对字符串进行排序。 PHP 5.4.0 中新增的。      
	1. SORT_FLAG_CASE  - 能够与 SORT_STRING  或 SORT_NATURAL  合并（OR 位运算），不区分大小写排序字符串。      

1. **返回值**    
	成功时返回 TRUE ， 或者在失败时返回 FALSE 。     

