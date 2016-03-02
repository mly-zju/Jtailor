一款非常轻量级的头像上传组件，使用html5的canvas技术实现头像的裁剪，并使用ajax上传到指定地址。使用方法如下：

下载源码，将Jtailor.js存入你的工程目录下，然后在你需要的文件中导入。
同时需要注意，由于该组件依赖于jQuery，所以使用之前请先确保导入了jQuery。

作为组件使用，在html中引入下面的代码：

	<div class='jtailor_avatar_wrapper'>
		<img src='' alt='等待上传' class='jtailor_avatar'/>
		<button class="jtailor_avatar_upload">上传头像</button>
	</div>

其中最外层的div的class可以用户自行设置，方便使用即可。同时在js中导入一行代码：$('.jtailor_avatar_wrapper').avatar_init();
这样即可快速使用。如果需要定制，avatar_init()方法提供了下述参数：
post_url: 设置图片需要上传的目的地地址，默认为空。
post_name: 设置图片上传post的名称，默认为空。服务端可以通过post_name来获得上传的图片数据。
size_level: 设置组件尺寸的大小，共有big,small,middle三种选项，对应的裁剪后的头像尺寸分别为150px*150px,70px*70px,100px*100px。默认为middle。
success: function(data){};是一个ajax成功后的回调函数，其中data为ajax返回的值。默认为空函数。
fail: function(data){};是一个ajax失败后的回调函数，其中data为ajax返回的值。默认为空函数。

通过设置这些参数，用户可以将组件应用于自己的需求中。比如，可以：
$('.jtailor_avatar_wrapper').avatar_init({post_url: 'example.com', post_name: 'mine_avatar', size_level: 'big', success: function(data){alert(data);}});

组件可以和其他html元素配合使用，构建丰富的页面，一个简单的应用demo见源码demo1.html，你也可以在线看效果：http://7xovdy.com1.z0.glb.clouddn.com/Jtailor_2/demo1.html
