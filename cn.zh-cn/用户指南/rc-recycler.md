# rc-recycler<a name="cce_01_0126"></a>

## 插件简介<a name="section1636442645315"></a>

rc-recycler是一款可根据用户配置策略对资源进行自动回收的插件。用户可在创建或者在插件运行过程中对具体的回收策略进行调整。该插件能定期清理集群中的无用资源，保证其他功能的正常运行。

## 约束与限制<a name="section1968316128568"></a>

-   仅支持1.9和1.11版本的CCE集群中安装本插件。
-   只支持default命名空间的job清理，当前支持特性：Job资源并行回收、日志转储、回收统计信息、缓存机制为分次list请求。

## 安装插件<a name="section1842517810574"></a>

1.  登录CCE控制台，单击左侧导航栏的“插件管理“，在“插件市场“页签下，单击rc-recycler插件下的“安装插件“。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  <a name="li1959342211297"></a>参照[表1](#table95961922132915)配置插件安装参数。

    **表 1**  安装插件说明

    <a name="table95961922132915"></a>
    <table><thead align="left"><tr id="row160342282920"><th class="cellrowborder" valign="top" width="24%" id="mcps1.2.3.1.1"><p id="p2605142202915"><a name="p2605142202915"></a><a name="p2605142202915"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="76%" id="mcps1.2.3.1.2"><p id="p15606112216299"><a name="p15606112216299"></a><a name="p15606112216299"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row06061022132913"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p15608722202910"><a name="p15608722202910"></a><a name="p15608722202910"></a>扫描间隔</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p18655207173318"><a name="p18655207173318"></a><a name="p18655207173318"></a>完成一次扫描后间隔多少时间进行下一次扫描 (单位：秒)</p>
    </td>
    </tr>
    <tr id="row19610422192916"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p1861292242911"><a name="p1861292242911"></a><a name="p1861292242911"></a>完成保留时间</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p7759143153417"><a name="p7759143153417"></a><a name="p7759143153417"></a>Job资源在到达完成状态后保留在集群内的时间 (单位：分)</p>
    <a name="ul193942114612"></a><a name="ul193942114612"></a><ul id="ul193942114612"><li>-1：永远保留完成状态的Job</li><li>0：一旦Job变成完成状态就将其回收</li></ul>
    </td>
    </tr>
    <tr id="row1961532212297"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p36171422142912"><a name="p36171422142912"></a><a name="p36171422142912"></a>失败保留时间</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p114061739143411"><a name="p114061739143411"></a><a name="p114061739143411"></a>Job资源在到达失败状态后保留在集群内的时间（单位：分）</p>
    <a name="ul116872577912"></a><a name="ul116872577912"></a><ul id="ul116872577912"><li>-1：永远保留失败状态的Job</li><li>0：一旦Job变成失败状态就将其回收</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

4.  配置完成后，单击“安装”。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 升级插件<a name="section23441939916"></a>

1.  登录CCE控制台，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击“rc-recycler“下的“ 升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。
    >-   升级“rc-recycler“插件时，会替换原先节点上的旧版本的“rc-recycler“插件，安装最新版本的“rc-recycler“插件以实现功能的快速升级。

2.  在基本信息页面选择插件版本，单击“下一步“。
3.  参考[安装插件](#li1959342211297)中参数说明配置参数后，单击“升级“即可升级“rc-recycler“插件。

## 卸载插件<a name="section8166134965710"></a>

1.  登录CCE控制台，单击左侧导航栏的“插件管理“，在“插件实例“页签下，选择对应的集群，单击rc-recycler下的“卸载“。
2.  在弹出的窗口中，单击“是“，可卸载该插件。

