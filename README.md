```ng-repeat```是过滤删选数据的必备神器。

它是Angular自带的指令(directive),关于指令以后会详细介绍，这是非常有特色的东西。
ng-repeat就好像Javascript的for循环，我们依次访问数组中的对象，满足要求的返回true,就会显示在页面上。不满足要求的返回false，隐藏起来。

ng-repeat的用法也相当简单，基本格式是```对象 in 集合```，然后在它封装的HTML元素中，$scope上就多了我们声明的对象变量，可以直接访问。
有多少个对象，这个元素就在页面上显示多少次。

更强大的是ng-repeat可以用 ｜加上filter,想加多少个就用多少个|。只有经过层层选拔的数据才会进行repeat一个个显示到页面上。
ng-repeat经常作用的HTML元素包括```<tr>```,```<li>```，分别在```<table>```和```<ul>```这种天然的集合性质的元素中。

唯一要注意的是ng-repeat作用的集合中不能有元素是相同的(Javascript中的===)，原因是ng-repeat会自动追踪集合中每个对象，
如果有变化就自动更新页面(果然是神器),所以必须能区分每个对象。

如果不能做到所有集合的元素都不同(通常Javascript的基本类型都会出现),可以用```对象 in 集合 track by $index```的写法，
ng-repeat就不会抱怨了。```$index```也是ng-repeat暴露给页面的关键词，可以直接使用判断对象的序号。