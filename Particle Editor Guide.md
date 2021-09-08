---


---

<p>back to the <a href="./README.md">Overview</a>.</p>
<h1 id="particle-editor-guide">粒子编辑指南</h1>
<p>欢迎来到 <strong>粒子编辑指南</strong>.<br>
本指南将帮助你接触编辑器，并解释粒子效果的基本功能。无论你是一个完全的初学者或已经有一些接触编辑器，这里是最好的地方开始!</p>
<!-- 本指南将帮助你接触编辑器，并解释粒子效果的基本功能。无论你是一个完全的初学者或已经有一些接触编辑器，这里是最好的地方开始! -->
<h2 id="content">Content</h2>
<ul>
<li><a href="#the-tool">The Tool</a>
<ul>
<li><a href="#menu">菜单</a></li>
<li><a href="#preview">预览</a></li>
<li><a href="#functions">功能</a></li>
<li><a href="#properties">属性</a></li>
<li><a href="#controls">控制</a></li>
<li><a href="#current-assets">流动资产</a></li>
</ul>
</li>
<li><a href="#functions-1">功能</a>
<ul>
<li><a href="#base-properties">基本属性</a></li>
<li><a href="#emitter">发射器</a></li>
<li><a href="#initializer">初始化器</a></li>
<li><a href="#operator">操作符</a></li>
<li><a href="#force-generator">力发电机</a></li>
<li><a href="#constraint">约束</a></li>
<li><a href="#renderer">渲染器</a></li>
<li><a href="#pre-emission-operator">前发射操作符</a></li>
</ul>
</li>
<li><a href="#what-now">接下来是什么</a></li>
</ul>
<h2 id="the-tool">这个工具</h2>
<p>(<a href="https://developer.valvesoftware.com/wiki/Dota_2_Workshop_Tools/Particles/Particle_Editor">阀门工具的官方文档</a>)</p>
<p>有两种方法打开粒子编辑器:第一种是点击主资源浏览器窗口左上角的火焰符号，打开一个空白的新窗口。第二种方法是直接打开已有的粒子效果，在资源浏览器中双击它。</p>

<p>现在打开一个已经存在的粒子效果作为例子:</p>
<p>注意:如果你不能打开一个粒子，并收到一个错误消息与<code>没有相应的内容文件</code>，你不能编辑这个粒子效果，因为阀门只使编译的版本公开。</p>
<h3 id="menu">菜单</h3>
<p>在左上角，您有标准的菜单操作文件，编辑，查看和帮助。没有什么特别的，只是一些默认操作，如保存，打开等
这里重要的注意:为了修改阀门粒子，你需要保存它在你当前的插件。</p>
<h3 id="preview">Preview</h3>
<p>你的窗口的最大部分应该填充在中间的预览部分。在这里你可以看到最终在游戏中的效果。您可以使用WASD、鼠标右键和鼠标滚轮自由移动，从任意侧面和距离观看效果。左上方有两行文本，显示粒子数量的统计信息。
<br>
顶部栏中的图标主要处理预览窗口中效果的回放。在这里您可以停止模拟，重新启动它，等等。<br>
<img src="https://i.imgur.com/ktpuMb6.png" alt=""><br>
在右边还有两个按钮，可以用来重置相机，例如，如果你已经导航相机不利。<br>
<img src="https://i.imgur.com/jMP5TY3.png" alt="alt text"><br>
行中的最后一个按钮是最重要的:可视化允许以图形方式显示各种属性，否则是不可见的。它会打开一个额外的小窗口，在那里您可以选择您想要显示的内容。<br>
<img src="https://i.imgur.com/Mj7G1HC.png" alt="alt text"><br>
最重要的是第一项 <code>可视化属性，Visualize Attributes</code> 它允许你显示特定的属性，如半径，alpha等。同时, <code>显示控制点，Show Control Points</code> 上面显示了所有的控制点。如果信息过多，请禁用 <code>包括子系统，Include Child Systems</code> 忽略子效应数据，to ignore the child effect data。</p>
<h3 id="functions">Functions</h3>
<p>函数是每个粒子效应的核心。在这里，您可以定义所有属性和行为，使效果是什么。在上半部分，还有4个小按钮，使导航更容易.</p>
<p><img src="https://i.imgur.com/XppFQIR.png" alt="alt text"></p>
<p>如果你在粒子编辑器中同时打开多个效果，你可以用左箭头跳转到最后一个显示的效果。同样，向右的箭头指向下一个效果。右边的按钮是灰色的，显示一个P或一个数字。如果当前效果作为子效果添加到另一个效果中，您可以使用它来显示这些效果的列表并跳转到它们。反之，它旁边的按钮带有数字或大写c。这显示了树结构中的从属效果。如果这两个按钮是不可点击的，这意味着目前没有可用的效果。<br>
更多关于功能的细节在这里:<a href="#Functions-1">函数</a>.</p>
<h3 id="properties">Properties</h3>
<p>此处显示当前选定功能的详细数据。如果您想对其中一个函数进行更改，这里是正确的地方。<br>
<img src="https://i.imgur.com/VLjTtIz.png" alt=""></p>
<h3 id="controls">控制，Controls</h3>
<p>控制部分分为两个部分:控制点和预览。控制点是构成粒子效果和代码之间的界面的三维向量。它们将允许你将粒子效果精确地放置在你想要的地方，并让你控制各种行为。<br>
<img src="https://i.imgur.com/1OU3mSS.png" alt="alt text"><br>
通过单击箭头右侧的彩色图标，可以直接影响这些点，例如通过移动或旋转它们。或者，您也可以在它旁边的字段中输入您想要的值。在最右边你会发现一个小的锁符号。如果它是关闭的，输入的值将被保存，以便下次在粒子编辑器中打开这个效果时，值将立即恢复到保存的值。通过下面的预览部分，其他资产(如模型)可以直接加载到当前效果中。这只是一个测试工具，对游戏显示的最终结果没有影响。然而，对于快速测试不同的效果是必要的。</p>
<h3 id="current-assets">流动资产，Current Assets</h3>
<p>这部分就像一个小资产浏览器，可以用来重新打开(焦点)当前打开的粒子效果，而不离开粒子编辑器。在大多数情况下，你可以/应该最小化它，为你的预览和其他窗口提供更多的空间。<br>
<img src="https://i.imgur.com/OgFzSDw.png" alt=""></p>
<h2 id="functions-1">Functions</h2>
<p>既然您已经了解了该工具的一般处理方法，我们可以开始更仔细地了解使每个效果工作的函数。函数被分为不同的组，将在这里解释。你可以在这里找到所有函数及其用法的完整列表: <a href="./Function%20Library.md">函数库</a><br>
要向其中一个组添加函数，只需单击加号图标并从列表中选择一个元素。您还可以选择多个功能与<strong>ctrl</strong> or <strong>shift</strong> and copy, 剪切和粘贴知道快捷方式 (<em>ctrl + c, ctrl + x, ctrl + v</em>).这些动作贯穿多个粒子效果.</p>
<p><strong>其他重要的注意:</strong><br>
所有函数都是基于优先级的。有时两个相同的函数一起工作，但有时只有一个函数是活动的。在这种情况下，或者当两个函数有一个相似的用例时，只有最后添加的一个是活动的。因此，位于组底部的函数具有最高的优先级.</p>
<h3 id="base-properties">基本属性，Base Properties</h3>
<p>基本属性包含关于效果的所有信息，包括所有其他组。此外，初始值和其他重要值都可以在这里找到。下面解释一些可以在这里设置的初始值。这些属性与你的效果中的每一个粒子相关联，并且彼此独立</p>
<ul>
<li><code>color</code> - 粒子着色的颜色.</li>
<li><code>radius</code> - 决定了这个粒子的大小.</li>
<li><code>lifetime</code> -  这是以秒为单位的时间，你的粒子会活着，这意味着它会在这段时间之后被摧毁.</li>
<li>其他人，others</li>
</ul>
<p>如果在效果的其他地方更改了这些属性，它们将被覆盖.<br>
这里最重要的一个领域是 <code>马克斯粒子</code> 这是一个硬上限的粒子数量，最大允许的这个效应(不包括子效应)。</p>
<h3 id="emitter">发射器，Emitter</h3>
<p>发射器是可以生成粒子的函数。因此，它们几乎可以在每种效应中找到。通常使用一种发射器就足够了。其中最常用的发射器是:</p>
<ul>
<li><code>不断排放，Emit continuously</code> - 在设定的时间间隔内发射粒子。 <code>发射率，emission rate</code> 是每秒发射的粒子数吗, <code>发射时间，emission duration</code> 粒子发射的持续时间和<code>排放开始时间，emission start time</code> 发射开始的延迟是以秒为单位吗. (<a href="./Function%20Library.md#emit-continuously">库</a>)</li>
<li><code>发出的瞬间，Emit instantaneously</code> - 发出，emits <code>粒子数排放，num to emit</code> 粒子直接在一开始的效果。发射可以延迟 <code>排放开始时间，emission start time</code>. (<a href="./Function%20Library.md#emit-instantaniously">库</a>)</li>
</ul>
<h3 id="initializer">初始化器，Initializer</h3>
<p>初始化器通常只在创建粒子时执行一次。在它们的帮助下，粒子得到了它们的初始值。如果没有初始化器，效果几乎无法实现，特别是因为它们在操作符中扮演着最重要的角色之一:粒子的位置.<br>
初始化器通常用于设置一些随机的初始值:</p>
<ul>
<li><code>生命中随机，Lifetime random</code> - 将生成粒子的生命周期设置为介于之间的随机值 <code>终身时间，lifetime min</code> and <code>生命终点，lifetime max</code>. (<a href="./Function%20Library.md#lifetime-random">库</a>)</li>
<li><code>半径随机，Radius random</code> - 设置生成粒子的半径为一个随机值 <code>半径最小值，radius min</code> and <code>半径最大值，radius max</code>. (<a href="./Function%20Library.md#radius-random">库</a>)</li>
<li><code>旋转随机,Rotation random</code> -将粒子的初始旋转随机化 <code>偏航偏移量最小,yaw offset min</code> and <code>偏航偏移量最大,yaw offset max</code> plus <code>偏航初始,yaw initial</code> 除此之外。主要是 <code>Roll</code> 这个重要的领域对于基本的精灵来说重要吗. <code>随机翻转方向,randomly flip direction</code> 是否可以检查以处理最小值和最大值，就像它们被否定了一样. (<a href="./Function%20Library.md#rotation-random">库</a>)<br>
<em>这里有更多关于旋转的信息: <a href="./Tutorials/Rotation%20Guide.md">旋转指南</a></em></li>
<li><code>颜色随机,Color Random</code> - 设置初始颜色为之间的随机向量 <code>color 1</code> and <code>color 2</code>. 暂时忽略所有其他字段，它们很少被使用。 (<a href="./Function%20Library.md#color-random">Library</a>)</li>
<li><code>Alpha random</code> - 在两者之间随机设置alpha值<code>alpha min</code> and <code>alpha max</code>. (<a href="./Function%20Library.md#alpha-random">库</a>)</li>
</ul>
<p><em>注意:alpha是一个值，用来描述粒子的透明程度。0表示完全透明，255表示完全固体.</em></p>
<p>除了这些随机值初始化器，位置初始化器是最重要的。它们决定一个粒子将在哪里产生。此外，它们有很多领域需要调整，基本原理如下:</p>
<ul>
<li><code>球内位置随机,Position within sphere random</code> -最常用的位置初始化器。在中心控制点周围给定半径内的随机位置放置新粒子，可以用 <code>控制点数量,control point number</code>. 每个粒子之间的距离是随机选择的<code>初始距离,distance min</code> and <code>距离 max</code>.  初始化器也可以用来将粒子放置在一个精确的位置，通过让两个距离值都为0。有关其他字段的更多信息，请查询(<a href="./Function%20Library.md#position-within-sphere-random">Library</a>)</li>
</ul>
<p><em>用法:这个初始化器可以被使用，无论何时你只是想把一个粒子放在一个CP位置。但用粒子填充整个球体也是很有用的。</em></p>
<ul>
<li><code>位置在环,Position along Ring</code> -第二常用的位置初始化器。沿着半径可设定的环放置新粒子 <code>初始半径,initial radius</code>.与一个<code>厚度,thickness</code> 大于0时，粒子在一定距离内随机放置 &lt; <code>厚度,thickness</code> 围绕“正常”环位置。粒子在环上随机分布。如果你想改变这个，请检查 <code>均匀分布,even distribution</code>. 这个选项迫使所有粒子沿着环均匀地产生。与<code>均匀分布数,even distribution count</code> 你可以控制，需要多少粒子来放置一个完整的环，否则(-1)它们是基于总粒子数分布的。 (<a href="./Function%20Library.md#position-along-ring">Library</a>)</li>
</ul>
<p><em>用法:这个初始化器主要用于创建粒子的闭合环，例如向外传播的环波。它对螺旋也很有用.</em></p>
<ul>
<li><code>路径顺序位置,Position on path sequential</code> -沿着两个控制点之间的路径放置新粒子。因此，这个初始化器经常用于绳子、链条等。 <code>起始控制点数,start control point number</code> and <code>终点控制点数,end control point number</code>定义粒子放置的位置. <code>粒子从开始映射到结束</code> 是否需要粒子的数量来填充路径和<code>最大距离,maximum distance</code> 限制路径的长度，如果两个CPs彼此太远. <code>在开始点和结束点之间使用顺序CP对</code> 在开始和结束之间使用所有的CP数，所以它可以用来绘制像正方形(开始、结束和2在中间)这样的形状。 (<a href="./Function%20Library.md#position-along-path-sequential">Library</a>)</li>
</ul>
<p><em>用途:主要用于光束(如激光)、闪电或链，但也可用于沿形状定位粒子，如三角形或矩形。</em></p>
<p>还有更多的位置初始化器，但它们大多是非常具体的，因此在需要时进行说明。然而，还有一个初始化器是非常常用的放置粒子:</p>
<ul>
<li><code>位置修正偏移随机,Position modify offset random</code> - 不是在位置初始化器定义的位置生成粒子，而是在这个点周围的一个随机位置生成粒子. <code>抵消 min</code> and <code>抵消 max</code>定义允许粒子生成的框。. (<a href="./Function%20Library.md#position-modify-offset-random">库</a>)</li>
</ul>
<p><em>用法:类似于' 球内位置随机 '，但用的是一个方框而不是一个球体。虽然只能使用一个位置初始化器，但这个可以添加到其他所有初始化器之上.</em></p>
<p>初始化器的另一个重要用途是速度生成器。这些可以在粒子产生后直接给它们一个运动方向。一般的速度和运动将在后面加以说明.</p>
<h3 id="operator">操作符</h3>
<p>操作符是对所有粒子都有持久影响的函数，只要它们还活着。它们与初始化器一起创建任何效果的主要功能.</p>
<p>每种粒子效应都应使用一种算符:a <strong>decay</strong> 操作符。衰变定义，当你创造的粒子被杀死时如何结束。如果没有定义衰变，粒子引擎就不知道如何处理旧粒子，也根本不会删除它们。为了防止这种情况，预览会显示一条警告信息:<br>
<img src="https://i.imgur.com/SRRSIs6.png" alt=""></p>
<p>现在我们来看看最常见的衰变算子:</p>
<ul>
<li><code>寿命衰减,Lifespan decay</code> -这个操作符杀死每一个超过其生命周期的粒子。 (<a href="./Function%20Library.md#lifespan-decay">库</a>)</li>
</ul>
<p>正如一开始所描述的，每个粒子都有自己的生命周期。只要这个操作符是激活的，当这个持续时间结束时，粒子就会被删除。这个操作符没有太多的选项，因为它的工作很简单(但非常重要)。但是要注意，如果你想要有永远不会死的粒子(忽略生命周期)，你可以改变<code>操作符结束覆盖状态,operator end cap state</code>从-1到1 ,from -1 to 1 (endcap状态一般稍后解释).</p>
<p>所有其他衰变操作符都有非常具体的用例，并将在需要时进行解释。</p>
<p>下一组重要的运营商是淡出。他们可以用很少的努力有很大的效果，并被普遍使用.</p>
<ul>
<li><code>阿尔法淡入简单,Alpha fade in simple</code> - 设置粒子的alpha值为0，并增加它直到它达到初始的alpha值。它所花费的时间可以定义为 <code>时间比例衰减,proportional fade in time</code>,这是基于粒子寿命的。 (<a href="./Function%20Library.md#alpha-fade-in-simple">库</a>)</li>
<li><code>淡出很简单,Alpha fade out simple</code> -  与淡入相同，但在生命周期结束时将alpha降低为0。淡出开始时间可以用 <code>比例衰减时间,proportional fade out time</code>.  (<a href="./Function%20Library.md#alpha-fade-out-simple">库</a>)</li>
<li><code>颜色褪色,Color fade</code> -不断地改变粒子的颜色，从最初的颜色 <code>颜色褪色,Color fade</code>.开始和结束时间可以用 <code>渐渐开始时间,fade start time</code> and <code>消失结束时间,fade end time</code>, 两者都与粒子寿命成正比。与 <code>输出字段,output field</code>, 这个操作符还可以缩放粒子的其他矢量属性(但很少使用).  (<a href="./Function%20Library.md#color-fade">库</a>)</li>
<li><code>半径范围内,Radius scale</code> - 基本上不是退色，但工作原理很相似。根据粒子的寿命不断地改变粒子的半径。缩放从 <code>开始规模,start scale</code> and is done at <code>end time</code>. The radius starts with,半径开始于 <code>半径开始规模,radius start scale</code> - 乘以初始值，以<code>半径结束规模,radius end scale</code> - 乘以初始值。与 <code>轻松进出,ease in and out</code>线性缩放被平滑的曲线所取代。 <code>规模的偏见,scale bias</code> 同时控制缩放速度。较高的偏差值(最大值为1.0)将使粒子在开始时缩放更快，然后平滑.  (<a href="./Function%20Library.md#radius-scale">库</a>)</li>
</ul>
<p>另一个非常有用和常用的操作符是:</p>
<ul>
<li><code>移动锁定到控制点,Movement lock to control point</code> -  使所有粒子随着控制点的移动而移动 <code>控制点数量,control point number</code>. 每次CP移动，粒子就会移动相同的方向和距离。这将是1比1的比率(然而它可以是控制器与衰落字段下面，需要时解释).  (<a href="./Function%20Library.md#movement-lock-to-control-point">库</a>)</li>
</ul>
<p>还有两个操作符，它们支持一组其他操作符、初始化式等。这两个是:</p>
<ul>
<li><code>旋转的基本,Rotation basic</code> -是大多数持续改变粒子旋转(滚转、偏航、俯仰)的动作所需要的. (<a href="./Function%20Library.md#rotation-basic">库</a>)</li>
<li><code>运动的基本,Movement basic</code> - 是大多数运动粒子的函数所需要的，如速度、力等。如果你希望你的粒子移动，但它们没有，你应该检查这个操作符是否已经添加。它也可以应用重力效应，可以控制<code>重力,gravity</code>.在大多数情况下，只使用z坐标，它也可以有负值. <code>drag</code> 是一个值，它控制粒子随时间的减慢程度，就像摩擦力一样。当阻力为0时，粒子将永远以相同的速度运动，当阻力增大时，粒子会随着时间的推移减慢速度(1.0为最大值). (<a href="./Function%20Library.md#movement-basic">库</a>)</li>
</ul>
<p>还有很多非常有用的操作符，但最重要的几个已经在上面解释过了。其他操作符将在以后的教程中使用。</p>
<h3 id="force-generator">力发电机</h3>
<p>力发生器是一个函数它对粒子施加某种力来移动它们. <code>Movement basic</code> 必须使用它们。使用这些绝对是更先进的在可能不是显而易见的第一次，但他们可以取得巨大的效果。下面简要解释一下最常用的方法:</p>
<ul>
<li><code>拉向控制点,Pull towards control point</code> - 不断施加一个力，把所有粒子都拉向一个给定的物体 <code>控制点数量,control point number</code>. 它可以是负的<code>大量的力量,amount of force</code>有排斥的效果这个力不断地加到当前速度上，导致速度稳步增加。的<code>下降,falloff</code> 力量类似于从运动基本阻力。因为它的默认值是2，它(几乎)总是需要减少，以使这个力发生器工作. (<a href="./Function%20Library.md#pull-towards-control-point">库</a>)</li>
</ul>
<h3 id="constraint">约束,Constraint</h3>
<p>约束是所有函数中使用最少的，并且可能对性能有最大的影响。然而，它们非常强大，提供了非常有用的功能。因此，只有在你确切地知道你想用它达到什么目的时，你才应该使用它。其中一些将在后续教程中进行解释.</p>
<h3 id="renderer">渲染器,Renderer</h3>
<p>我们之前看到的所有其他函数都影响到不可见的抽象粒子，即具有位置、大小、颜色等属性的对象。<br>
渲染器现在可以让我们看到这些抽象的粒子。他们决定我们是展示单个火花，一条长链，还是模型。它们不是每个粒子效果所必需的，但需要添加到每个用户可以看到的粒子上。通常只使用一个渲染，但没有限制，可以同时使用多个渲染，使用上面描述的粒子对象.</p>
<p>我们将看看一些常见的渲染器和它们的重要属性:</p>
<ul>
<li><code>渲染精灵,Render sprites</code> -最常用的“基本”渲染。在粒子位置显示带有精灵纹理的2D平面，它总是面向摄像机，这样就可以实现3D对象的效果.
<ul>
<li>再往下走，就有 <code>纹理,texture</code>, 最重要的领域。如果你按下小放大镜按钮，一个资源浏览器窗口将打开，为这个精灵选择一个新的纹理.</li>
<li><code>取向类型,>orientation type</code> 设置精灵的面向方向。通常情况下 <code>屏幕上对齐,Screen Align</code>, 所以它总是面对着摄像机。但随着 <code>World-Z对齐</code> or <code>粒子正常对齐,Particle Normal Align</code> 还可以达到其他效果.</li>
<li><code>颜色和alpha调整</code> 是一组设置为彩色显示相关的东西，并且经常更改。因为这对多个渲染器来说几乎是一样的，它将在后面解释.</li>
<li><code>半径范围内,Radius Scale</code>乘以这个特定精灵的当前半径。如果同时使用多个精灵渲染器，这将非常有用.</li>
<li><code>alpha 规模,Alpha Scale</code> 与半径范围内相似，Radius Scale，只是alpha值不同。</li>
<li><code>颜色混合，Color blend</code> 改变精灵的颜色(通过初始化器和操作符改变其他颜色后应用)</li>
<li>其他属性可以根据需要进行解释</li>
<li>(<a href="./Function%20Library.md#render-sprites">库</a>)</li>
</ul>
</li>
</ul>
<p><em>用法:几乎用于所有用途。也可以动画，这是经常用于火焰和爆炸.</em></p>
<ul>
<li><code>Render rope，渲染的绳子</code> -用于绘制连接的拉伸纹理，连接多个粒子对象。像半径，颜色，alpha等属性在这些点之间被插值。对于小径，绳索，链条，横梁非常有用。它将根据粒子索引连接粒子顺序(可以用开头描述的“可视化”函数查看)
<ul>
<li>与渲染精灵的大多数方式相同</li>
<li><code>Closed loop，闭环</code>将最后一个粒子和第一个粒子联系起来。在与位置沿环初始化器的组合中非常有用</li>
<li><code>Reverse point order，反向点订单</code> 在检查时将连接顺序从升序改为降序(关于粒子索引)</li>
<li><code>Texture Coordinates，纹理坐标</code> 是一个设置集合，用于显示纹理，如何拉伸等等。也可以在渲染精灵中使用，但在这里更常用. <code>纹理V世界大小</code>控制纹理的拉伸因子，增加这个值通常是好的，否则纹理会感觉被压缩. <code>texture V Scroll Rate，纹理V滚动率</code> 添加一个滚动效果的纹理，可以有很大的效果，当纹理是无缝的(和更有效的移动粒子)</li>
<li>(<a href="./Function%20Library.md#render-rope">库</a>)</li>
</ul>
</li>
</ul>
<p><em>用途:用于戒指、闪电或其他光束。也可以用来创建沿路径的地面效果.</em></p>
<ul>
<li><code>Render models，渲染模型</code> -在粒子位置渲染模型。用它来表示小的粒子数。渲染的模型是显示的，但不能进行交互，所以它们不能被选择，没有点击框等。然而，它们在视觉上的行为与真实世界的物体相同，所以它们可以被照亮并投射阴影.
<ul>
<li>渲染精灵中的一些字段也可以在这里找到</li>
<li><code>models，模型</code>是呈现的模型列表。默认为空，您可以通过单击+图标添加新模型，展开视图并在打开的资产浏览器中选择一个模型.</li>
<li><code>material override，材料覆盖</code>用另一种材料替换模型使用的材料.</li>
<li><code>ignore normal，忽略正常</code> 是最简单的解决方案，使您的模型直立，如果它躺在它的一侧。只有当你不想对模型做进一步的旋转时才使用这个.</li>
<li><code>animated，动画</code> 可以检查以启用渲染模型的动画。许多其他属性都与此设置相关联。后面会有更详细的解释吗.</li>
<li><code>disable shadows，禁用的阴影</code> 可以检查为这个模型禁用阴影吗</li>
<li>(<a href="./Function%20Library.md#render-models">库</a>)</li>
</ul>
</li>
</ul>
<p><em>用法:用于所有其他渲染器无法完成的事情。特别是在动画方面，可能性几乎是无穷无尽的.</em></p>
<p>重要注意:只有一个渲染器可以激活每个粒子效果。如果您想要呈现多个模型，请使用多个效果或在模型字段中添加多个模型.</p>
<ul>
<li><code>Render sprite trail，渲染精灵路线</code> - 与精灵的行为类似，但取决于粒子速度。注意，如果你第一次添加这个渲染器，粒子可能是不可见的，只要你的粒子不移动。粒子的速度越快，所选纹理的长度就越长。他们是非常有用的小道(惊喜!)，但也条纹和其他创造性的应用程序。他们通常需要 <code>trail length，路的长度</code> 粒子的属性.
<ul>
<li>与渲染精灵基本相同</li>
<li><code>max length，最大长度</code> 最大拉伸长度是多少</li>
<li><code>min length，最小长度</code> 最小拉伸长度是多少</li>
<li><code>head / tail ...，头/尾</code> 颜色，alpha，半径比例，就像渲染精灵。然而，可以分别设置的头和尾的踪迹(插入之间).</li>
<li><code>ignore delta time，忽略时间增量</code> 可以在不移动它们的情况下模拟精灵轨迹速度。也可以在大多数速度操作符和初始化器上激活(在这种情况下不需要基本的运动).</li>
<li>(<a href="./Function%20Library.md#render-sprite-trail">库</a>)</li>
</ul>
</li>
</ul>
<p><em>用法:主要用作路径，它们通常与普通精灵一起工作。是否可以更方便地在3D空间中定位精灵.</em></p>
<ul>
<li><code>Render deferred light，呈现递延光</code> - 在粒子周围投射彩色光的光源。因为它只是延迟的光，没有阴影将被投下. (<a href="./Function%20Library.md#render-deferred-light">库</a>)</li>
</ul>
<p><em>注意:延迟光是一种面向性能的照明方法。它将照亮/着色所有附近的物体基于他们的法线。这种光不会投射阴影，也不会照亮物体后面的其他物体.</em></p>
<ul>
<li><code>Render projected，渲染预计</code> -  渲染其他物体上的材质，如地面，树木等。很可能在粒子编辑器中是不可见的，为了避免这种情况，去控制面板，点击中间的“浏览”按钮选择一个模型(搜索“地面”并选择一个平面模型通常是有用的)。这里还需要注意的是，与所有其他基于纹理的渲染相比，这个渲染器需要一个材质 (.vtex &lt;-&gt; .vmat). (<a href="./Function%20Library.md#render-projected">库</a>)</li>
</ul>
<p><em>用途:用于地面效果，如跺脚，裂缝，或冰冻地面。也可以影响其他型号，这是特别有用的烧伤痕迹。</em></p>
<p>有更多的渲染器，但这些是最常见的.</p>
<h3 id="pre-emission-operator">前发射操作符</h3>
<p>在这个类别下是运算符，在所有其他函数之前计算。他们经常操纵儿童保护局，操纵儿童等等。大多数粒子效果不需要它们，但它们可以是一个伟大的添加，对于一些复杂的粒子行为是至关重要的.</p>
<p>因为它们中的大多数都有非常具体的用例，所以这里只介绍最常见的用例:</p>
<ul>
<li><code>设置单控制点位置</code> - 将另一个控制点的协调复制到一个新的控制点。新的可以有一个抵消原来的一个，在 <code>控制点位置</code>. 这个偏移考虑了原始控制点的方向，因此是在局部空间中。如果你想避免这种情况，请勾选 <code>set positions in world space</code>. 当原有CP发生变化时，新的CP会不断重新计算。如果你想避免这种情况，请勾选 <code>only set position once，只设置一次位置</code>. (<a href="./Function%20Library.md#set-single-control-point">Library</a>)</li>
<li><code>设置控制点位置</code> -  基本与上面相同，但可以一次做4个新的CP。 (<a href="./Function%20Library.md#set-control-point-positions">Library</a>)</li>
</ul>
<p>请注意，当控制点由这些Pre - Emission操作符之一设置时，它们将在控制面板中变成灰色，不能再手动更改。它们也无法改变 <code>SetParticleControl，设置粒子控制</code> 从代码或任何其他方法。所以这些CP只在内部使用.</p>
<h2 id="what-now">现在?</h2>
<p>现在你应该对不同函数的区别有一个基本的了解。但还有更多的东西要学习，这在这里没有涵盖.</p>
<p>现在你可以去探索资产浏览器，查找不同的粒子效果，试着理解它们并尽可能多地进行实验.</p>
<p>如果你不想自己解决问题，你可以直接去看后续教程。这些将加深您的知识，并对特定的用例和效果进行更详细的介绍。所以去看看这些链接:</p>
<ul>
<li><a href="./Tutorials.md#guided-tutorial">指导教程</a></li>
</ul>

