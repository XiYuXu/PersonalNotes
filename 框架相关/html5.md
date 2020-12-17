视频与音频代码模板:
<audio controls= "controls">
    <src="filepath">
    <src="filepath">
</audio>

拖动代码模板:
<div id="drap1" ontrop="allowDrop()" ondragover="allowDrag()">
<img src="nimei.jpg" onstart="Drag()" draggable="true">
有两个element需要设置,一个是要拖动的对象,一个是放置拖动对象的对象.
有四个表示:
对放置拖动对象的对象:设置为可放置,
                        allowDrop(event){ event.preventDefault(); }     //阻止默认处理(在新窗口打开)
                   设置放置动作:
                        Drop(event){ev.preventDefault(); data=event.transfom.getData("");event.target.appendChild(node);}
对要拖动的对象     :设置拖动的东西,并保存拖动的数据
                        Drag(event){ event.dataTransfer.setData("nimei",event.target.id);}




