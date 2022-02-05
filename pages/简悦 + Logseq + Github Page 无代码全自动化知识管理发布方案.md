> 在简悦标注，自动生成符合 Logseq 的标注文件，然后发布到 Github Page 的无代码化全自动方案。

- # 感谢
	- [@tiensonqin](https://twitter.com/tiensonqin) 提供了这么棒的双链笔记 Logseq，得益于 [@pengx17](https://twitter.com/pengx17) 发布的 [Logseq Publish GitHub Action](https://pengx17.github.io/knowledge-garden/#/page/logseq publish github action)，可以非常方便的使用 Logseq 编写，使用 Git 发布它。
- # 流程
  	> 整个工作流包含两种方案
	- 当你在 Logseq 页面的任何改动都会自动发布到你的 Github Page 上面， 你看到的 [这篇教程](https://kenshin.wang/knowledge-garden/) 就是此方式发布的。
	  id:: 61fdfac4-f85b-4d3a-a8eb-2f094ceb90ca
		- <iframe src="https://cdn.jsdelivr.net/gh/23784148/upload-images@main/simpered/article/2022-02-05_10-49-53.mp4" height="350" 
		  id:: 61fdf9cc-9e20-43c6-bce6-e11d453319f0
		  id:: 61fdf9cc-9e20-43c6-bce6-e11d453319f0
		  id:: 61fdf933-8821-41e8-8525-74acb0f6138e
		  id:: 61fdf55a-49d3-4471-b629-d804de8d6ff3
		  id:: 61fdf259-655e-4778-87d7-fc3e7b2ebf1d
		  scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>
	- 在简悦中的任意标注都会发布到你的 Github Page 上面
	  id:: 61fdfb06-622e-417f-9047-7bb17d9a25a9
	  			#+BEGIN_TIP
	   在 Web 端使用简悦标注，并通过简悦的同步助手自动将以 Markdown 形式的标注导入到 Logseq page 文件夹，并使用 Hazel（或 crontab ）自动 Push 到 Github repo 后通过 Logseq Publish GitHub Action 自动发布的全流程无代码自动化发布方案。
	   #+END_TIP
		- <iframe src="https://cdn.jsdelivr.net/gh/23784148/upload-images@main/simpered/article/2022-02-05_11-24-17.mp4" height="350" 
		  id:: 61fdf9cc-36e8-44b9-9a99-a4a40af098f4
		  id:: 61fdf933-6df1-4e8b-8d71-3e9b7cec0653
		  id:: 61fdf55a-2cf2-4e79-b3f4-f5b14d86611e
		  id:: 61fdf259-0e0d-4c14-9364-d567abae56a6
		  scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>
# 为什么是 Logseq
	- Logseq 支持 outliner 层级结构，类似 Workflowy / Roam Research 的效果，每层都可以延伸为一个「新的 Page」，非常适合「知识的生长」。
	- 虽然 Obsidian Publish 也提供发布功能，但定制化程度不如 Logseq 且只能 Host 在它的服务器上面。
	- 基于 Local first，因此非常适合跟简悦搭配一起做知识管理。
# 平台
	- 简悦（含同步助手）
	- Logseq
	- Github Page +  [Logseq Publish GitHub Action](https://pengx17.github.io/knowledge-garden/#/page/logseq publish github action)
- # 配置
	- #+BEGIN_TIP
	  关于 Github Page + Logseq + Logseq Publish GitHub Action 的配置。
	  #+END_TIP
	- ## 简单配置
		- Clone https://github.com/23784148/knowledge-garden 到本地。
		- 设置你的 Logseq  到此文件夹。
		- Push 到你的 Repo & 设置 Github Page。
	- ## 详细配置
	  > 下面的内容是详细配置，方便你理解整个配置过程。
		- 建立 一个新的 [Public repo](https://github.com/new)
			- ![image-20220204120717831](https://cdn.jsdelivr.net/gh/23784148/upload-images@main/typora/20220204_1643947637.png)
		- 打开 [Logseq Publish GitHub Action](https://github.com/pengx17/knowledge-garden/blob/main/.github/workflows/main.yml) 并复制 `main.yaml` 里面的内容，然后在上一步建立的 repo 下建立一个新的 Action。
			- ![image-20220204121011522](https://cdn.jsdelivr.net/gh/23784148/upload-images@main/typora/20220204_1643947811.png){:height 596, :width 621}
			  
			  >（将上步得到的内容）粘贴其中，按下图所示操作，然后点击 Start commit 后不用更改其它内容，直接选择 **Commit new file** 即可。 
			  
			  ![image-20220204121443402](https://cdn.jsdelivr.net/gh/23784148/upload-images@main/typora/20220204_1643948083.png)
		- 将 Logseq 库文件设置到（ Clone 后的）文件夹。
			- ![image-20220204122559854](https://cdn.jsdelivr.net/gh/23784148/upload-images@main/typora/20220204_1643948759.png)
			        
			  > 如果设置无误的话此文件夹应该是下图所示的文件结构。
			  
			  ![image-20220204122728407](https://cdn.jsdelivr.net/gh/23784148/upload-images@main/typora/20220204_1643948848.png)
		- 设置主题和样式，为便捷使用，我直接将下面的文件复制
			- [custom.css](https://github.com/23784148/knowledge-garden/blob/main/logseq/custom.css) 复制到 `logseq` 里面。
			- [logseq dev theme.md](https://github.com/23784148/knowledge-garden/blob/main/pages/logseq dev theme.md) 复制到 `pages` 里面。
			- [config.edn](https://github.com/23784148/knowledge-garden/blob/main/logseq/config.edn) 复制到 `logseq` 里面。
			      
			  > 打开 Logseq 并进入 logseq dev theme 后会看到如下的截图内容，说明样式设置成功。
			  
			  ![image-20220204123647416](https://cdn.jsdelivr.net/gh/23784148/upload-images@main/typora/20220204_1643949407.png)
		- 将全部文件提交到 Github，当提交后会自动进行 Actions 操作，会有下图所示的效果。
			- ![image-20220204145022733](https://cdn.jsdelivr.net/gh/23784148/upload-images@main/typora/20220204_1643957422.png)
			      
			  > 进入 Settings → Pages，并按下图所示选择，设置 `gh-pages` 为 Github Page 分支，然后点击 **Save**。
			  
			  ![image-20220204130245584](https://cdn.jsdelivr.net/gh/23784148/upload-images@main/typora/20220204_1643950965.png)
			      
			  > 然后回到 Actions，如果出现下图所示的效果说明配置成功。
			  
			  ![image-20220204145114193](https://cdn.jsdelivr.net/gh/23784148/upload-images@main/typora/20220204_1643957474.png)
			      
			  > 回到 Page 页面，根据截图所示访问你的 Github Page
			  
			  ![image-20220204145337453](https://cdn.jsdelivr.net/gh/23784148/upload-images@main/typora/20220204_1643957617.png)
		- 访问 `<上图所示的地址>#/page/logseq dev theme` 比如这个教程 [所示的例子](https://kenshin.wang/knowledge-garden/#/page/logseq%20dev%20theme) 会得到下图所示的内容，则说明配置成功。
		  
		  ![image-20220204145601034](https://cdn.jsdelivr.net/gh/23784148/upload-images@main/typora/20220204_1643957761.png)
- # 自动化
	- #+BEGIN_TIP
	  当 `page` 文件夹有改动时，自动 Push Github。
	  #+END_TIP
	- ## Hazel
		- 自动化方案选择是 Hazel 这个监控文件夹变化而进行一系列自动化操作的 Mac App，如果你是 Windows 用户可以使用 [Dropit](http://www.dropitproject.com/)。
			- ![](https://cdn.jsdelivr.net/gh/23784148/upload-images@main/simpered/article/SCR-20220204-pa8.png)
			- （对上图）简单的说明
				- 除了监控 `page` 文件夹外也可以是其它文件夹 e.g. `journals` `logseq` `assets` 甚至于监控根目录的 `README.md`（当此文件改动时再提交）。
				- 为了降低执行的频率，文件改动一分钟后再执行，这里的数字可以改为任意值。
				- Shell 代码很简单，就是 Push 到 Github
				  ```
				  cd /<your path>/knowledge-garden
				  git add .
				  git commit -m "auto save:Update some logseq pages."
				  git push origin main
				  ```
		- ## crontab
			- #+BEGIN_NOTE
			  如果你没有 Hazel 的话，也可以使用 `crontab` 方案，也就是每隔 xxx 时间自动调用上面这个 bash 文件，如何使用可以看 [这篇文章](https://mp.weixin.qq.com/s/w6-LQLAApN7HhXaBwslegw) 。
			  #+END_NOTE
- # 简悦设置
	- #+BEGIN_TIP
	  利用简悦的 [自动化](http://ksria.com/simpread/docs/#/自动化) 与 同步助手的 [增强导出](https://kb.simpread.pro/#/page/增强导出) 功能。
	  #+END_TIP
	- ## 标准方案
		- #+BEGIN_TIP
		  此方案的前提是：使用简悦的知识库功能，如何配置 [请看这里](https://kb.simpread.pro/#/page/建立知识库)。
		  #+END_TIP
			- 在标注的自动化上增加 **导出 Markdown** 的功能。
				- ![](https://cdn.jsdelivr.net/gh/23784148/upload-images@main/simpered/article/SCR-20220204-pxe.png){:height 368, :width 652}
				  id:: 61fd073f-383c-482b-a04b-12b9461463dd
			- 使用简悦官方适配的 [Logseq Markdown 模板](https://github.com/Kenshin/simpread/discussions/2153#discussioncomment-2109959)，将模板代码粘贴到 **选项页 → 服务 → 定制化**。
			  ![](https://cdn.jsdelivr.net/gh/23784148/upload-images@main/simpered/article/SCR-20220204-q7r.png)
			- 设置 Hazle 监控 `output` 变化，当出现 `.md` 文件时，自动转移（或复制）到 `pages` 文件夹下面。
			  id:: 61fd073f-a4ec-41e8-af00-e76a6bc62000
			  ![](https://cdn.jsdelivr.net/gh/23784148/upload-images@main/simpered/article/SCR-20220204-qbl.png){:height 177, :width 621}
			  > 也可仅迁移文件名含有 `xxxx@annote.md` 的文件。
			  
			  ![](https://cdn.jsdelivr.net/gh/23784148/upload-images@main/simpered/article/SCR-20220205-g8s.png)
	- ## 简易方案
	  #+BEGIN_TIP
	  此方案仅配置 **增强导出** 和 **稍后读 & 标注的自动化**，适合轻量级使用简悦的用户。
	  #+END_TIP
		- 配置 [增强导出](https://kb.simpread.pro/#/page/增强导出)
		   #+BEGIN_TIP
		   如果不使用知识库的话，可以将增强导出的文件夹目录设置为 `pages` 文件夹。
		   #+END_TIP
		- 配置稍后读的自动化
		  ![](https://cdn.jsdelivr.net/gh/23784148/upload-images@main/simpered/article/SCR-20220204-qgb.png)
		- 配置标注的自动化，与标准方案时一致 ((61fd073f-383c-482b-a04b-12b9461463dd))
		- ((61fd073f-a4ec-41e8-af00-e76a6bc62000)) （与标准方案时一致）
		  #+BEGIN_TIP
		  引申：如果不使用同步助手的话也可以实现，即：
		  将 Hazel 监控 Chrome 下载文件夹，当遇到 `xxxx@annote.md` 文件时，自动转移到 `pages` 文件夹即可。
		  #+END_TIP
- # 至此
	- id:: 61fdf55a-23b9-429d-996d-797c43827be9
	  > 全部配置结束，上述配置包含
		- ((61fdfac4-f85b-4d3a-a8eb-2f094ceb90ca))
		  id:: 61fdf55a-6c68-46ba-884b-ee36441e3062
		- ((61fdfb06-622e-417f-9047-7bb17d9a25a9))
		  id:: 61fdf55a-1fd9-4ee7-a05b-b36acb897b16
- # 此方案的优缺点
	- ## 优点
		- 无代码化的全自动操作方案。
		- 一次配置即可。
		- 除 Github Page 外，其余均为 Local first 产品，此流程可保证最大稳定性。
		- 发布的站点支持手机端访问。
		- Logseq 可支持粘贴本地图片（到 `assets` 文件夹）配合 Hazel 自动提交功能，相当于拥有了自己的「图床方案」。
	- ## 缺点
		- 如果不是 Mac 用户或无法使用 Hazel 的话，效果不会那么完美。
		- Logseq 因为是所见即所得的编辑方案，稳定性和切换编辑/预览效果没有 Typora 好。
		- Logseq 并不是属于标准的 Markdown 结构（细节 [看这里](https://www.markdownguide.org/tools/logseq/)），所以再加上双链的话，迁移有一定成本。（可适度使用 Logseq [导出功能](((61fdf55a-0377-4d51-8d83-d98ef4f785fa))) 改善此问题）
		  id:: 61fdf259-3039-4977-8772-fd84e9207f76
- # 附录
	- ## 导出为 Markdown
	  id:: 61fdf55a-0377-4d51-8d83-d98ef4f785fa
		- Logseq 自带了导出功能，可根据下图所示的方式导出为 Markdown，因为对 [部分 Markdown 语法的不支持](https://www.markdownguide.org/tools/logseq/)，尤其是 `Ordered Lists` 所以导入的 Markdown 还需要手动修改。
		  ![](https://cdn.jsdelivr.net/gh/23784148/upload-images@main/simpered/article/SCR-20220205-gft.png)
	- ## 更多例子
		- {{embed ((61fe1b3a-8356-4f20-b8f1-f5f4ed21ee7b))}}