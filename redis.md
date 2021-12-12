创建集群时，关于BUG：…cannot load such file -- redis (LoadError)的解决方法
原因：

缺少 redis 的相关依赖，需要通过 gem 安装

执行命令：

sudo gem install redis

	
(公)81.70.6.39 
(内)10.0.24.8