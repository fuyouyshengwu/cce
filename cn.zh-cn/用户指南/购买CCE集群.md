# 购买CCE集群<a name="cce_01_0028"></a>

您可以通过云容器引擎控制台非常方便快速的创建Kubernetes集群。Kubernetes是大规模容器集群管理软件，一个集群可以管理一组节点资源。

CCE集群支持虚拟机与裸金属服务器混合、支持GPU、NPU等异构节点的混合部署，基于高性能网络模型提供全方位、多场景、安全稳定的容器运行环境，您可以实现多种场景的混合部署。

## 约束与限制<a name="section1386743114294"></a>

-   创建节点过程中会使用域名方式从OBS下载软件包，需要能够使用云上内网DNS解析OBS域名，否则会导致创建不成功。为此，节点所在子网需要配置为[内网DNS地址](https://support.huaweicloud.com/dns_faq/dns_faq_002.html)，从而使得节点使用内网DNS。在创建子网时DNS默认配置为内网DNS，如果您修改过子网的DNS，请务必**确保子网下的DNS服务器可以解析OBS服务域名**，否则需要将DNS改成内网DNS。
-   单Region下单用户可创建的集群总数限制为50个，如果配额不满足业务需求，请[到“我的配额”提交申请](https://console.huaweicloud.com/quota/?locale=zh-cn#/quota)。
-   集群一旦创建以后，不支持变更以下项：
    -   变更集群类型，例如“鲲鹏集群“变更为“CCE集群“。
    -   变更集群的控制节点数量。
    -   变更控制节点可用区。
    -   变更集群的网络配置，如所在的虚拟私有云VPC、子网、容器网段、服务网段、IPv6、kubeproxy代理（转发）模式。
    -   变更网络模型，例如“容器隧道网络“更换为“VPC网络“。


更多内容请参见[约束与限制](https://support.huaweicloud.com/productdesc-cce/cce_productdesc_0005.html)。

## 操作步骤<a name="section463761220269"></a>

1.  登录CCE控制台，在总览页面单击“购买Kubernetes集群“，或在左侧导航栏中单击“资源管理  \>  集群管理”，单击“CCE集群“右侧的“购买”按钮。

    **图 1**  集群管理-购买CCE集群<a name="fig11806912127"></a>  
    ![](figures/集群管理-购买CCE集群.png "集群管理-购买CCE集群")

2.  参照[表1](#table8638121213265)设置集群参数，其中带“\*”的参数需重点关注。

    **表 1**  创建集群参数配置

    <a name="table8638121213265"></a>
    <table><thead align="left"><tr id="row10638181262612"><th class="cellrowborder" valign="top" width="20.02%" id="mcps1.2.3.1.1"><p id="p1063821214265"><a name="p1063821214265"></a><a name="p1063821214265"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="79.97999999999999%" id="mcps1.2.3.1.2"><p id="p1638181232617"><a name="p1638181232617"></a><a name="p1638181232617"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1922964644615"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p9231104613468"><a name="p9231104613468"></a><a name="p9231104613468"></a>计费模式</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><a name="ul463941414445"></a><a name="ul463941414445"></a><ul id="ul463941414445"><li><span class="keyword" id="keyword66602077459"><a name="keyword66602077459"></a><a name="keyword66602077459"></a>包年/包月</span>：预付费模式，按订单的购买周期计费，适用于可预估资源使用周期的场景，价格比按需计费模式更优惠。包年/包月集群创建后不能删除，如需停止使用，请到<a href="https://account.huaweicloud.com/usercenter/#/userindex/retreatManagement" target="_blank" rel="noopener noreferrer">费用中心</a>执行退订操作。</li><li><span class="keyword" id="keyword44309542597"><a name="keyword44309542597"></a><a name="keyword44309542597"></a>按需计费</span>：后付费模式，按资源的实际使用时长计费，可以随时开通/删除资源。</li></ul>
    <p id="p0624127506"><a name="p0624127506"></a><a name="p0624127506"></a>本章以<span class="uicontrol" id="uicontrol8978171712013"><a name="uicontrol8978171712013"></a><a name="uicontrol8978171712013"></a>“按需计费”</span>类型为例进行讲解。</p>
    </td>
    </tr>
    <tr id="row42961494311"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p812874116011"><a name="p812874116011"></a><a name="p812874116011"></a>区域</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p161283411302"><a name="p161283411302"></a><a name="p161283411302"></a>不同区域的云服务产品之间内网互不相通；请就近选择靠近您业务的区域，可减少网络时延，提高访问速度。</p>
    </td>
    </tr>
    <tr id="row12321131519262"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p14322181522614"><a name="p14322181522614"></a><a name="p14322181522614"></a>企业项目</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p19409193818259"><a name="p19409193818259"></a><a name="p19409193818259"></a>该参数仅对开通企业项目的企业客户帐号显示。</p>
    <p id="p1363744211114"><a name="p1363744211114"></a><a name="p1363744211114"></a>选择某企业项目（如：default）后，集群、集群下节点、集群安全组、节点安全组和自动创建的节点EIP（弹性公网IP）将创建到所选企业项目下。为方便管理资源，在集群创建成功后，建议不要修改集群下节点、集群安全组、节点安全组的企业项目。</p>
    <p id="p73221815122618"><a name="p73221815122618"></a><a name="p73221815122618"></a>企业项目是一种云资源管理方式，企业项目管理服务提供统一的云资源按项目管理，以及项目内的资源管理、成员管理。了解更多企业项目相关信息，请查看<a href="https://support.huaweicloud.com/usermanual-em/zh-cn_topic_0123692049.html" target="_blank" rel="noopener noreferrer">企业管理</a>。</p>
    </td>
    </tr>
    <tr id="row1063812126263"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p15639812122620"><a name="p15639812122620"></a><a name="p15639812122620"></a>* 集群名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p26391512172614"><a name="p26391512172614"></a><a name="p26391512172614"></a>新建集群的名称，创建后不可修改。</p>
    <p id="p1520317181911"><a name="p1520317181911"></a><a name="p1520317181911"></a>集群名称长度范围为4-128个字符，以小写字母开头，由小写字母、数字、中划线（-）组成，且不能以中划线（-）结尾。</p>
    </td>
    </tr>
    <tr id="row6649879161231"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p1769363161231"><a name="p1769363161231"></a><a name="p1769363161231"></a>版本</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p9100682161231"><a name="p9100682161231"></a><a name="p9100682161231"></a>Kubernetes社区基线版本，建议选择最新的版本。版本升级请参见<a href="集群升级概述.md">集群升级概述</a>。</p>
    <p id="p1022520483"><a name="p1022520483"></a><a name="p1022520483"></a>若有<strong id="b20728225518"><a name="b20728225518"></a><a name="b20728225518"></a>Beta</strong>版本时，您可以选择试用，但不建议您将该版本用于商用场景。</p>
    </td>
    </tr>
    <tr id="row572593234714"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p14725432104718"><a name="p14725432104718"></a><a name="p14725432104718"></a>集群管理规模</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p14899102111550"><a name="p14899102111550"></a><a name="p14899102111550"></a>集群管理规模是指当前集群的控制节点可以管理的最大工作节点规模，您可以选择50节点、200节点、1000节点或2000节点（仅1.15.11及以上版本的集群支持）的管理规模，请根据您的业务需求选择。如果您需要创建5000节点规模的集群，请<a href="https://console.huaweicloud.com/quota/?locale=zh-cn#/quota" target="_blank" rel="noopener noreferrer">提交工单</a>申请。</p>
    <p id="p192696516218"><a name="p192696516218"></a><a name="p192696516218"></a>若选择<span class="uicontrol" id="uicontrol35596531909"><a name="uicontrol35596531909"></a><a name="uicontrol35596531909"></a>“1000节点”</span>，表示当前集群的控制节点最多可管理1000个工作节点。由于不同管理规模的控制节点规格不同，因此配置费用会有差异。</p>
    </td>
    </tr>
    <tr id="row17367436403"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p16736194318408"><a name="p16736194318408"></a><a name="p16736194318408"></a>控制节点数</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p67371743164017"><a name="p67371743164017"></a><a name="p67371743164017"></a><strong id="b6722821483"><a name="b6722821483"></a><a name="b6722821483"></a>3：</strong>集群将创建三个控制节点，从而实现集群高可用，在单个控制节点发生故障后集群可以继续使用，不影响业务功能。单击“更改”，在“容灾设置”窗口，可进行如下设置：</p>
    <p id="p1459193512420"><a name="p1459193512420"></a><a name="p1459193512420"></a><strong id="b1213333014433"><a name="b1213333014433"></a><a name="b1213333014433"></a>容灾级别：</strong></p>
    <a name="ul196515617488"></a><a name="ul196515617488"></a><ul id="ul196515617488"><li>可用区：通过把控制节点建在不同的可用区，达到容灾目的。</li><li>故障域：通过把控制节点建在同一可用区下不同故障域，达到容灾目的。当环境支持故障域时，才会显示该选项。</li><li>主机：通过把控制节点建在同一可用区下不同主机，达到容灾目的。</li><li>自定义：您可以自行选择每个控制节点的位置。故障域模式控制节点必须在同一可用区下。</li></ul>
    <p id="p14985022174110"><a name="p14985022174110"></a><a name="p14985022174110"></a><strong id="b131651325480"><a name="b131651325480"></a><a name="b131651325480"></a>1：</strong>集群仅创建一个控制节点，单控制节点集群不保证SLA（服务级别协议），非高可用集群，不适用于商用场景。单击“更改”，在“可用区设置”页面可选择控制节点可用区。</p>
    <div class="note" id="note15800847104112"><a name="note15800847104112"></a><a name="note15800847104112"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ul1869875074110"></a><a name="ul1869875074110"></a><ul id="ul1869875074110"><li>在商用场景中，为提高集群容灾能力，建议您选择多控制节点模式集群。</li><li>多控制节点模式开关在集群创建完成后不可变更。单控制节点集群不支持升级为多控制节点集群，控制节点故障将影响运行业务，请谨慎选择。</li><li>为保证可靠性，1000及以上集群管理规模默认开启多控制节点模式。</li></ul>
    </div></div>
    </td>
    </tr>
    <tr id="row1763991215268"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p15639181282617"><a name="p15639181282617"></a><a name="p15639181282617"></a>* 虚拟私有云</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p20558173114298"><a name="p20558173114298"></a><a name="p20558173114298"></a>新建集群所在的虚拟私有云，集群创建后不可更改。</p>
    <p id="p116393128265"><a name="p116393128265"></a><a name="p116393128265"></a>虚拟私有云是通过逻辑方式进行网络隔离，提供安全、隔离的网络环境。</p>
    <p id="p1063941211266"><a name="p1063941211266"></a><a name="p1063941211266"></a>若没有虚拟私有云可选择，请单击<span class="uicontrol" id="uicontrol162261618154315"><a name="uicontrol162261618154315"></a><a name="uicontrol162261618154315"></a>“<span id="text112261418174320"><a name="text112261418174320"></a><a name="text112261418174320"></a>创建虚拟</span>私有云”</span>进行创建，完成创建后单击刷新按钮。操作步骤请参见<a href="https://support.huaweicloud.com/usermanual-vpc/zh-cn_topic_0013935842.html" target="_blank" rel="noopener noreferrer">创建虚拟私有云和子网</a>。</p>
    </td>
    </tr>
    <tr id="row15639412132615"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p36391812172618"><a name="p36391812172618"></a><a name="p36391812172618"></a>* 所在子网</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p924510014306"><a name="p924510014306"></a><a name="p924510014306"></a>节点虚拟机运行的子网环境，集群创建后不可更改。</p>
    <p id="p594513252114"><a name="p594513252114"></a><a name="p594513252114"></a>通过子网提供与其他网络隔离的、可以独享的网络资源，以提高网络安全。</p>
    <p id="p1108371202"><a name="p1108371202"></a><a name="p1108371202"></a>若没有子网可选择，请单击<span class="uicontrol" id="uicontrol626432718115"><a name="uicontrol626432718115"></a><a name="uicontrol626432718115"></a>“<span id="text82642277119"><a name="text82642277119"></a><a name="text82642277119"></a>创建子网</span>”</span>进行创建，完成创建后单击刷新按钮。虚拟私有云、子网、集群的关系请参见<a href="集群概述.md">集群概述</a>。</p>
    <p id="p1369519572172"><a name="p1369519572172"></a><a name="p1369519572172"></a>创建节点过程中会使用域名方式从OBS下载软件包，需要能够使用内网DNS解析OBS域名，否则会导致创建不成功。为此，节点所在子网需要配置为<a href="https://support.huaweicloud.com/dns_faq/dns_faq_002.html" target="_blank" rel="noopener noreferrer">内网DNS地址</a>，从而使得节点使用内网DNS。在创建子网时DNS默认配置为内网DNS，如果您修改过子网的DNS，请务必<strong id="cce_01_0028_b8921731141716"><a name="cce_01_0028_b8921731141716"></a><a name="cce_01_0028_b8921731141716"></a>确保子网下的DNS服务器可以解析OBS服务域名</strong>，否则需要将DNS改成内网DNS。</p>
    <p id="p9619101653511"><a name="p9619101653511"></a><a name="p9619101653511"></a><strong id="b1119161703511"><a name="b1119161703511"></a><a name="b1119161703511"></a>集群创建后子网无法修改，请谨慎选择。</strong></p>
    </td>
    </tr>
    <tr id="row115671413307"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p16567134113303"><a name="p16567134113303"></a><a name="p16567134113303"></a>IPv6双栈</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p36131511317"><a name="p36131511317"></a><a name="p36131511317"></a>默认不开启。<strong id="b3710124814376"><a name="b3710124814376"></a><a name="b3710124814376"></a>该功能仅在1.15及以上版本的集群下显示，方法请参见<a href="https://support.huaweicloud.com/bestpractice-cce/cce_bestpractice_00222.html" target="_blank" rel="noopener noreferrer">通过CCE搭建IPv4/IPv6双栈集群</a>。</strong></p>
    <p id="p1656714414305"><a name="p1656714414305"></a><a name="p1656714414305"></a>开启IPv6：开启后将自动创建IPv6地址的容器网段与服务网段，支持通过IPv6地址段访问集群资源，包括节点，工作负载等。</p>
    </td>
    </tr>
    <tr id="row482955911270"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p9831659192715"><a name="p9831659192715"></a><a name="p9831659192715"></a>网络模型</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p135701052194711"><a name="p135701052194711"></a><a name="p135701052194711"></a>集群创建成功后，网络模型不可更改，请谨慎选择。如何选择网络模型请参见<a href="https://support.huaweicloud.com/bestpractice-cce/cce_bestpractice_00162.html" target="_blank" rel="noopener noreferrer">CCE集群创建时如何选择网络模型？各模型的区别是什么？</a></p>
    <p id="p6806448162015"><a name="p6806448162015"></a><a name="p6806448162015"></a><strong id="b75401805214"><a name="b75401805214"></a><a name="b75401805214"></a>VPC网络</strong></p>
    <p id="p1319614613446"><a name="p1319614613446"></a><a name="p1319614613446"></a>VPC网络模式下每个节点占用一条VPC路由规则，Console界面中可显示当前局点支持的VPC路由规则条数，以及每个节点可供分配的容器IP个数（即可创建的Pod实例数目上限）。</p>
    <a name="ul68480277225"></a><a name="ul68480277225"></a><ul id="ul68480277225"><li>采用VPC路由方式与底层网络深度整合，适用于高性能场景，但每个节点占用一条VPC路由规则，节点数量受限于虚拟私有云VPC的路由配额。</li><li>VPC网络集群下的每个节点将会被分配固定大小的IP地址段，由于没有隧道封装的消耗，容器网络性能相对于容器隧道网络有一定优势。VPC网络集群由于VPC路由中配置有容器网段与节点IP的路由，可以支持集群外直接访问容器实例等特殊场景。<div class="note" id="note126721123118"><a name="note126721123118"></a><a name="note126721123118"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ul123221124171119"></a><a name="ul123221124171119"></a><ul id="ul123221124171119"><li>VPC网络模式下不支持扩展网段和NetworkPolicy。</li><li>一个VPC下创建多个VPC网络模式的集群时，需要为每个集群选择一个不重叠的地址段，不仅不能和VPC地址重叠，也不和其他容器网段重叠。</li></ul>
    </div></div>
    </li></ul>
    <p id="p0724144517209"><a name="p0724144517209"></a><a name="p0724144517209"></a><strong id="b952205617204"><a name="b952205617204"></a><a name="b952205617204"></a>容器隧道网络</strong></p>
    <p id="p9295195416117"><a name="p9295195416117"></a><a name="p9295195416117"></a>容器隧道网络下只能添加同一类型的节点，即全部为虚拟机节点或全部为裸金属节点。</p>
    <a name="ul1221141842110"></a><a name="ul1221141842110"></a><ul id="ul1221141842110"><li>基于底层VPC网络，另构建了独立的VXLAN隧道化容器网络，适用于一般场景。</li><li>VXLAN是将以太网报文封装成UDP报文进行隧道传输。容器网络是承载于VPC网络之上的Overlay网络平面，具有付出少量隧道封装性能损耗，即可获得通用性强、互通性强、高级特性支持全面（例如Network Policy网络隔离）的优势，可以满足大多数应用需求。</li></ul>
    </td>
    </tr>
    <tr id="row64648564171234"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p2042307171234"><a name="p2042307171234"></a><a name="p2042307171234"></a>容器网段</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p31209167171234"><a name="p31209167171234"></a><a name="p31209167171234"></a>请根据业务需求选择容器网段，确定容器网段后，容器实例将在规划的网段内分配IP，集群创建后该网段不可更改。</p>
    <a name="ul1423120351449"></a><a name="ul1423120351449"></a><ul id="ul1423120351449"><li>未勾选“自动选择”：请手动选择网段。若与子网网段有冲突时将有红色文字提示，请重新选择。建议使用网段：10.0.0.0/8~18，172.16.0.0/16~18，192.168.0.0/16~18。<p id="p158661543014"><a name="p158661543014"></a><a name="p158661543014"></a><strong id="b02629514118"><a name="b02629514118"></a><a name="b02629514118"></a>不同集群使用相同的容器网段，会导致容器IP冲突，应用访问异常。</strong></p>
    </li><li>勾选“自动选择”：系统将自动分配与子网网段无冲突的网段。</li></ul>
    <p id="p873618346117"><a name="p873618346117"></a><a name="p873618346117"></a>容器网段要设置合理的掩码，掩码决定集群内可用节点数量。集群中容器网段掩码设置不合适，会导致集群实际可用的节点较少。设置掩码后，选项下方会有当前网段最多支持的实例估算值，请作参考。详情请参见<a href="https://support.huaweicloud.com/bestpractice-cce/cce_bestpractice_00004.html" target="_blank" rel="noopener noreferrer">如何规划CCE集群的网络地址段？</a>。</p>
    </td>
    </tr>
    <tr id="row6775143217241"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p677653218246"><a name="p677653218246"></a><a name="p677653218246"></a>服务网段</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p977633218244"><a name="p977633218244"></a><a name="p977633218244"></a>服务网段为kubernetes service ip网段，集群创建后该网段不可更改。服务网段与已创建的路由不能冲突，如果冲突，请重新选择。</p>
    <a name="ul13104152611581"></a><a name="ul13104152611581"></a><ul id="ul13104152611581"><li>使用默认网段：默认设置为10.247.0.0/16网段。</li><li>手动设置网段：请根据业务需求设置合理的网段和掩码，掩码决定集群内可用service ip数量。</li></ul>
    <p id="p1325817337153"><a name="p1325817337153"></a><a name="p1325817337153"></a>详情请参见<a href="https://support.huaweicloud.com/bestpractice-cce/cce_bestpractice_00004.html" target="_blank" rel="noopener noreferrer">如何规划CCE集群的网络地址段？</a>。</p>
    </td>
    </tr>
    <tr id="row773511171567"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p37371717105616"><a name="p37371717105616"></a><a name="p37371717105616"></a>鉴权方式</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p2017413473382"><a name="p2017413473382"></a><a name="p2017413473382"></a><span class="uicontrol" id="uicontrol217464712384"><a name="uicontrol217464712384"></a><a name="uicontrol217464712384"></a>“RBAC”</span>默认选择，不可取消。</p>
    <p id="p16141515161117"><a name="p16141515161117"></a><a name="p16141515161117"></a>开启RBAC能力后，设置了细粒度权限的IAM用户使用集群下资源将受到权限控制。详细请参见<a href="命名空间权限（Kubernetes-RBAC授权）.md">命名空间权限（Kubernetes RBAC授权）</a>。</p>
    </td>
    </tr>
    <tr id="row1610917221609"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p6655100911"><a name="p6655100911"></a><a name="p6655100911"></a>认证方式</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p933784218111"><a name="p933784218111"></a><a name="p933784218111"></a>认证机制主要用于对集群下的资源做权限控制。</p>
    <p id="p1186713484551"><a name="p1186713484551"></a><a name="p1186713484551"></a>默认开启X509认证模式，X509是一种非常通用的证书格式。</p>
    <p id="p201651655441"><a name="p201651655441"></a><a name="p201651655441"></a>若需要对集群进行权限控制，请勾选“<strong id="b147071445995"><a name="b147071445995"></a><a name="b147071445995"></a>认证能力增强</strong>”，集群支持通过请求体的头域的信息识别用户，达到认证鉴权的目的。</p>
    <p id="p16929105085512"><a name="p16929105085512"></a><a name="p16929105085512"></a>用户需要分别上传自己的<strong id="b44714116510"><a name="b44714116510"></a><a name="b44714116510"></a>CA根证书</strong>、<strong id="b14669141413512"><a name="b14669141413512"></a><a name="b14669141413512"></a>客户端证书</strong>和<strong id="b6857112016516"><a name="b6857112016516"></a><a name="b6857112016516"></a>客户端证书私钥</strong>（证书制作方法可参考<a href="https://kubernetes.io/zh/docs/tasks/administer-cluster/certificates/" target="_blank" rel="noopener noreferrer">Certificates</a>），并勾选“<strong id="b458963217717"><a name="b458963217717"></a><a name="b458963217717"></a>我已确认上传的证书合法</strong>”。</p>
    <div class="caution" id="note173064357597"><a name="note173064357597"></a><a name="note173064357597"></a><span class="cautiontitle"> 注意： </span><div class="cautionbody"><a name="ul63601125729"></a><a name="ul63601125729"></a><ul id="ul63601125729"><li>请上传<strong id="b1324412411615"><a name="b1324412411615"></a><a name="b1324412411615"></a>小于1MB</strong>的文件，CA根证书和客户端证书上传格式支持<strong id="b142442413620"><a name="b142442413620"></a><a name="b142442413620"></a>.crt或.cer</strong>格式，客户端证书私钥仅支持上传<strong id="b5244124664"><a name="b5244124664"></a><a name="b5244124664"></a>未加密的证书私钥</strong>。</li><li>客户端证书有效期需要5年以上。</li><li>上传的CA根证书既给认证代理使用，也用于配置kube-apiserver聚合层，<strong id="b1507491567"><a name="b1507491567"></a><a name="b1507491567"></a>如不合法，集群将无法成功创建</strong>。</li></ul>
    </div></div>
    </td>
    </tr>
    <tr id="row463941216264"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p2063961212268"><a name="p2063961212268"></a><a name="p2063961212268"></a>集群描述</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p664014125268"><a name="p664014125268"></a><a name="p664014125268"></a>选填，请输入新建容器集群相应的描述信息。</p>
    </td>
    </tr>
    <tr id="row96582533813"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p2285145420345"><a name="p2285145420345"></a><a name="p2285145420345"></a>高级设置</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p1911106205716"><a name="p1911106205716"></a><a name="p1911106205716"></a>单击<span class="uicontrol" id="uicontrol151802714513"><a name="uicontrol151802714513"></a><a name="uicontrol151802714513"></a>“高级设置”</span>后展开详细项目，支持的功能如下（当前可用区中不支持的功能将隐藏）：</p>
    <p id="p113568261434"><a name="p113568261434"></a><a name="p113568261434"></a><strong id="b193562261439"><a name="b193562261439"></a><a name="b193562261439"></a>服务转发模式：</strong></p>
    <a name="ul1435618265318"></a><a name="ul1435618265318"></a><ul id="ul1435618265318"><li>iptables：社区传统的kube-proxy模式，完全以iptables规则的方式来实现service负载均衡。该方式最主要的问题是在服务多的时候产生太多的iptables规则，非增量式更新会引入一定的时延，大规模情况下有明显的性能问题。</li><li>ipvs：由华为主导开发并在社区获得广泛支持的kube-proxy模式，采用增量式更新，吞吐更高，速度更快，并可以保证service更新期间连接保持不断开，适用于大规模场景。<p id="p52781357485"><a name="p52781357485"></a><a name="p52781357485"></a>ipvs模式下，ingress和service使用相同的ELB实例时，无法在集群内的节点和容器中访问ingress。</p>
    </li></ul>
    <div class="note" id="note551324732117"><a name="note551324732117"></a><a name="note551324732117"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ul2513447132113"></a><a name="ul2513447132113"></a><ul id="ul2513447132113"><li>ipvs为大型集群提供了更好的可扩展性和性能。</li><li>ipvs支持比iptables更复杂的负载平衡算法（最小负载，最少连接，位置，加权等）。</li><li>ipvs支持服务器健康检查和连接重试等。</li></ul>
    </div></div>
    <p id="p2448659163311"><a name="p2448659163311"></a><a name="p2448659163311"></a><strong id="b15868154114358"><a name="b15868154114358"></a><a name="b15868154114358"></a>CPU管理策略：</strong></p>
    <p id="p658055813489"><a name="p658055813489"></a><a name="p658055813489"></a>该参数仅在v1.13.10-r0及以上版本的集群中显示。</p>
    <a name="ul14813182993518"></a><a name="ul14813182993518"></a><ul id="ul14813182993518"><li>开启：支持给工作负载实例配置CPU独占，适用于对CPU缓存和调度延迟敏感的工作负载。</li><li>关闭：关闭工作负载实例独占CPU核的功能，优点是CPU共享池的可分配核数较多。</li></ul>
    <p id="p1363818291491"><a name="p1363818291491"></a><a name="p1363818291491"></a>更多CPU管理策略内容请参见<a href="https://kubernetes.io/blog/2018/07/24/feature-highlight-cpu-manager/" target="_blank" rel="noopener noreferrer">Feature Highlight: CPU Manager</a>或<a href="https://bbs.huaweicloud.com/forum/thread-28901-1-1.html" target="_blank" rel="noopener noreferrer">深入理解 Kubernetes CPU Mangager</a>。</p>
    <p id="p14525175194312"><a name="p14525175194312"></a><a name="p14525175194312"></a>开启CPU管理策略之后，CCE节点变更规格将无法重新拉起或创建工作负载，解决方法详见<a href="https://support.huaweicloud.com/cce_faq/cce_faq_00189.html" target="_blank" rel="noopener noreferrer">CCE节点变更规格后，为什么无法重新拉起或创建工作负载？</a>。</p>
    </td>
    </tr>
    <tr id="row76532194177"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p79871037171719"><a name="p79871037171719"></a><a name="p79871037171719"></a>购买时长</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p1991143711174"><a name="p1991143711174"></a><a name="p1991143711174"></a>若选择创建<span class="uicontrol" id="uicontrol10197720111410"><a name="uicontrol10197720111410"></a><a name="uicontrol10197720111410"></a>“包年/包月”</span>的集群，请设置购买时长。</p>
    </td>
    </tr>
    </tbody>
    </table>

3.  单击“下一步：创建节点“，在“创建节点“步骤中，参照如下参数配置节点：
    -   **创建节点：**
        -   现在添加：创建集群的同时创建节点，当前仅支持虚拟机节点。如果节点创建失败集群会一起回滚。
        -   稍后添加：将不会创建节点，仅创建一个空集群，集群创建完成后可以添加虚拟机或裸金属节点。

    -   **计费模式：**支持“包年/包月“和“按需计费“两种计费类型。

        -   包年/包月：包年包月是预付费模式，按订单的购买周期计费，适用于可预估资源使用周期的场景，价格比按需计费模式更优惠。
        -   按需计费：按需计费是后付费模式，按资源的实际使用时长计费，可以随时开通/删除资源。

        创建集群时节点的计费方式跟随集群的计费方式，如集群的计费模式选择“按需计费“，则创建过程中节点的计费模式只能为“按需计费“，“包年/包月“同理。创建方式请参考[购买节点](购买节点.md)。

        包年/包月节点创建后不能删除，如需停止使用，请到[费用中心](https://account.huaweicloud.com/usercenter/#/userindex/retreatManagement)执行退订操作。

    -   **当前区域：**节点实例所在的物理位置。
    -   **可用区：**请根据业务需要进行选择。可用区是在同一区域下，电力、网络隔离的物理区域，可用区之间内网互通，不同可用区之间物理隔离。

        如果您需要提高工作负载的高可靠性，建议您在创建集群后将云服务器部署在不同的可用区，购买集群时节点只能部署在一个可用区。

        **图 2**  工作节点创建在不同可用区<a name="fig920914253210"></a>  
        ![](figures/工作节点创建在不同可用区.png "工作节点创建在不同可用区")

    -   **节点类型：**选择节点类型。
        -   虚拟机节点：选中后创建虚拟机节点。
        -   裸金属节点：创建集群过程中不可选，需在集群创建完成后才可以为集群增加裸金属节点。

            >![](public_sys-resources/icon-note.gif) **说明：** 
            >CCE集群中创建裸金属节点需满足以下条件：
            >-   集群创建完成之后才可以添加裸金属节点。
            >-   集群为非IPv6模式。
            >-   VPC网络集群版本高于v1.11.7，容器隧道网络集群版本高于v1.13.10。
            >-   节点计费模式为包年/包月。
            >购买裸金属节点请参考[购买节点](购买节点.md)。


    -   **节点名称：**自定义节点名称。长度范围为1-56个字符，以小写字母开头，支持小写字母、数字、中划线\(-\)，不能以中划线\(-\)结尾。

        创建后如需修改请参考[修改云服务器名称](https://support.huaweicloud.com/usermanual-ecs/ecs_03_0145.html)，修改后需要[同步节点信息](同步节点信息.md)。

    -   **节点规格：**请根据业务需求选择相应的节点规格。

        -   通用型：该类型实例提供均衡的计算、存储以及网络配置，适用于大多数的使用场景。通用型实例可用于Web服务器、开发测试环境以及小型数据库工作负载等场景。
        -   内存优化型：该类型实例提供内存比例更高的实例，可以用于对内存要求较高、数据量大的工作负载，例如关系数据库、NoSQL等场景。
        -   通用入门型：通用入门型实例提供均衡的计算、存储以及网络配置，利用CPU积分机制保证基准性能，适合平时不会持续高压力使用CPU，但偶尔需要提高计算性能完成工作负载的场景，可用于轻量级Web服务器、开发、测试环境以及中低性能数据库等场景。
        -   GPU加速型：提供优秀的浮点计算能力，从容应对高实时、高并发的海量计算场景。P系列适合于深度学习，科学计算，CAE等；G系列适合于3D动画渲染，CAD等。**仅支持1.11及以上版本集群添加GPU加速型节点。**
        -   高性能计算型：实例提供具有更稳定、超高性能计算性能的实例，可以用于超高性能计算能力、高吞吐量的工作负载场景，例如科学计算。
        -   通用计算增强型：该类型实例具有性能稳定且资源独享的特点，满足计算性能高且稳定的企业级工作负载诉求。
        -   磁盘增强型：该类型实例能提供可使用[本地磁盘存储](本地磁盘存储.md)以及更高网络性能的实例，可以用于处理需要高吞吐以及高数据交换处理的工作负载，例如大数据工作负载等场景。
        -   超高I/O型：该类型实例提供超低SSD盘访问延迟和超高IOPS性能，适用于高性能关系型数据库、NoSQL数据库（如Cassandra、MongoDB）、ElasticSearch搜索等场景。
        -   AI加速型：AI加速型节点实例，搭载高性能、低功耗的海思Ascend 310 AI处理器，实现快速高效地处理推理和图像识别等工作，适用于图像识别、视频处理、推理计算以及机器学习等场景。

            >![](public_sys-resources/icon-note.gif) **说明：** 
            >-   当前AI加速型节点仅在部分可用区可选。
            >-   选用AI加速型的节点前需要安装[huawei-npu](huawei-npu.md)插件，以保证使用昇腾 310芯片资源的负载可以正常运行。
            >-   节点创建成功后会安装D310芯片驱动并自动触发节点重启，期间会有短暂的节点不可用，属于正常现象，重启完成后可恢复正常。


        **图 3**  选择节点规格<a name="fig122133422328"></a>  
        ![](figures/选择节点规格.png "选择节点规格")

        为确保节点稳定性，系统会自动预留部分资源，用于运行必须的系统组件。详细请参见[节点预留资源计算公式](节点预留资源计算公式.md)。

    -   **操作系统：**部分Region不显示下方分类，请直接选择节点对应的操作系统。

        -   公共镜像：请选择节点对应的操作系统。

            公共镜像是常见的标准操作系统镜像，所有用户可见，包括操作系统以及预装的公共应用，更多介绍请参见[公共镜像概述](https://support.huaweicloud.com/productdesc-ecs/ecs_01_0049.html)。

        -   私有镜像（公测中）：包含操作系统或业务数据、预装的公共应用以及用户的私有应用的镜像，仅用户个人可见。**该功能仅支持v1.15及以上版本集群。**

            若没有私有镜像可选择，请参照[如何使用私有镜像制作工作节点镜像？（公测）](https://support.huaweicloud.com/bestpractice-cce/cce_bestpractice_00026.html)进行制作。

        -   共享镜像：由其他用户共享而来的私有镜像。更多关于共享镜像的使用，请参见[共享镜像](https://support.huaweicloud.com/usermanual-ims/ims_01_0305.html)。

        重装操作系统或修改操作系统配置将导致节点不可用，请务必谨慎操作，具体请参见[高危操作及解决方案](高危操作及解决方案.md)。

    -   **系统盘：**设置工作节点的系统盘空间。您可以设置系统盘的规格为40GB-1024GB之间的数值，缺省值为40GB。

        在默认情况下，系统盘可提供高I/O（SAS）、超高I/O（SSD）几种基本的云硬盘类型，关于云硬盘的详细信息请参见[云硬盘概述](https://support.huaweicloud.com/usermanual-ecs/ecs_03_0301.html)。

        加密：数据盘加密功能可为您的数据提供强大的安全防护，加密磁盘生成的快照及通过这些快照创建的磁盘将自动继承加密功能。**目前仅在部分Region显示此选项，具体以界面为准。**

        -   默认不加密。
        -   点选“加密“后，可在弹出的“加密设置“对话框中，选择已有的密钥，若没有可选的密钥，请单击后方的链接创建新密钥，完成创建后单击刷新按钮。

    -   <a name="li12223421320"></a>**数据盘：**设置工作节点的数据盘空间。您可以设置数据盘的规格为100GB-32768GB之间的数值，缺省值为100GB。数据盘可提供的云硬盘类型与上方系统盘一致。

        >![](public_sys-resources/icon-caution.gif) **注意：** 
        >若数据盘卸载或损坏，会导致docker服务异常，最终导致节点不可用。建议不要删除该数据盘。

        -   LVM管理：CCE数据盘使用LVM（Logical Volume Manager）进行磁盘管理，开启后您可以通过空间分配调整数据盘中不同资源的空间占比。第一块盘默认选中不可更改，新增数据盘后可开启或关闭该功能：
            -   默认选中，开启LVM管理。
            -   取消选中，关闭LVM管理。

                >![](public_sys-resources/icon-caution.gif) **注意：** 
                >-   开启LVM管理的数据盘将按照设置的比例进行统一分配。
                >-   1.13.10及更高版本的集群创建节点时，若未开启LVM管理的数据盘，请参考[给CCE集群的节点添加第二块数据盘](给CCE集群的节点添加第二块数据盘.md)填写安装前执行脚本进行格式化，否则该数据盘仍会被LVM管理。
                >-   1.13.10之前版本的集群创建节点时，若未开启LVM管理的数据盘请务必格式化，否则会与第一块数据盘进行二选一被LVM管理，进而导致与预期不符的情况。


        -   加密：数据盘加密功能可为您的数据提供强大的安全防护，加密磁盘生成的快照及通过这些快照创建的磁盘将自动继承加密功能。

            **该功能仅在部分Region的1.13.10及以上版本的集群中支持**，1.13.10之前版本的集群不显示此选项。

            -   默认不加密。
            -   点选“加密“后，可在弹出的“加密设置“对话框中，选择已有的密钥，若没有可选的密钥，请单击后方的链接创建新密钥，完成创建后单击刷新按钮。

        -   新增数据盘：当前仅支持挂载两块数据盘，您可以在节点创建完成后前往ECS添加更多数据盘。部分集群版本不支持此功能，具体以界面为准。
        -   数据盘空间分配：单击后方的![](figures/2020-08-28_101153.png)，可以对数据盘中的“k8s空间“和“用户空间“占比进行自定义设置，开启LVM管理的数据盘将按照设置的比例进行统一分配。部分集群版本不支持此功能，具体以界面为准。
            -   k8s空间：您可以自定义数据盘中Docker和Kubelet的资源占比。Docker资源包含Docker工作目录、Docker镜像数据以及镜像元数据；Kubelet资源包含Pod配置文件、密钥以及临时存储EmptyDir等挂载数据。

                Docker占比不能小于10%，且空间大小不能小于60G；Kubelet占比不能小于10%。

                Docker空间大小配置跟实际业务有关，详细的说明请参见[数据盘空间分配说明](数据盘空间分配说明.md)。

            -   用户空间：定义本地盘中不分配给kubernetes使用的空间大小和用户空间挂载路径。

                >![](public_sys-resources/icon-note.gif) **说明：** 
                >注意挂载路径不能设置为 /、/home/paas、/var/paas、/var/lib、/var/script、/var/log/、/mnt/paas、/opt/cloud，不能和系统目录冲突（例如bin、lib、home、root、boot、dev、etc、lost+found、mnt、proc、sbin、srv、tmp、var、media、opt、selinux、sys、usr等），否则会导致系统或节点安装失败。


        **当集群版本为v1.13.10-r0及以上，且节点规格为“磁盘增强型”或“超高I/O型”时，数据盘将显示如下选项：**

        -   云硬盘：与节点类型为非“磁盘增强型”或“超高I/O型”时的数据盘一致，此处不再赘述，详情参见上方的[数据盘](#li12223421320)。
        -   本地磁盘：本地磁盘实例有宕机风险，不保证数据可靠性，建议您使用**云硬盘**存储您的业务数据。

            本地磁盘配置参数如下：

            -   磁盘类型：节点类型为“磁盘增强型“时支持普通磁盘\(hdd\)；节点类型为“超高I/O型“时支持固态硬盘\(ssd\)。
            -   读写方式：当**存在多块本地盘时**可以设置读写方式，支持“串行“和“并行“两种方式。串行表示数据读写为线性模式，当一块盘使用完才会使用下一块；并行表示数据读写为条带模式，可以同时读写多块本地盘。
            -   k8s空间：您可以自定义数据盘中Docker和Kubelet的资源占比。Docker资源包含Docker工作目录、Docker镜像数据以及镜像元数据；Kubelet资源包含Pod配置文件、密钥以及临时存储EmptyDir等挂载数据。
            -   用户空间：定义本地盘中不分配给kubernetes使用的空间大小和用户空间挂载路径。

        >![](public_sys-resources/icon-notice.gif) **须知：** 
        >-   在数据盘中设置“k8s空间“和“用户空间“占比时，需满足k8s空间和用户空间总和为100%，设置后可单击![](figures/zh-cn_image_0220702939.png)自动调整数据。
        >-   磁盘使用direct-lvm模式，移除将使用loop-lvm模式，有影响系统稳定性的风险。

        **图 4**  设置本地磁盘<a name="fig831212511276"></a>  
        ![](figures/设置本地磁盘.png "设置本地磁盘")

    -   **虚拟私有云：**不可修改，仅用于展示当前集群所在的虚拟私有云，该参数仅在v1.13.10-r0及以上版本的集群中显示。
    -   **所在子网：**通过子网提供与其他网络隔离的、可以独享的网络资源，以提高网络安全。可选择该集群虚拟私有云下的任意子网，集群节点支持跨子网。

        创建节点过程中会使用域名方式从OBS下载软件包，需要能够使用内网DNS解析OBS域名，否则会导致创建不成功。为此，节点所在子网需要配置为[内网DNS地址](https://support.huaweicloud.com/dns_faq/dns_faq_002.html)，从而使得节点使用内网DNS。在创建子网时DNS默认配置为内网DNS，如果您修改过子网的DNS，请务必**确保子网下的DNS服务器可以解析OBS服务域名**，否则需要将DNS改成内网DNS。

        已有集群添加节点时，如果子网对应的VPC新增了扩展网段且子网是扩展网段，要在控制节点安全组（即集群名称-cce-control-随机数）中添加如下三条安全组规则，以保证集群添加的节点功能可用（新建集群时如果VPC已经新增了扩展网段则不涉及此场景）：

        ![](figures/004.png)

    -   **弹性IP：**独立申请的公网IP地址，若节点有互联网访问的需求，请选择“自动创建“或“使用已有“。**集群开启IPv6时，不显示该参数。**

        弹性公网IP提供外网访问能力，可以灵活绑定及解绑，随时修改带宽。未绑定弹性公网IP的云服务器无法直接访问外网，无法直接对外进行互相通信。详情请查看[弹性公网IP介绍](https://support.huaweicloud.com/usermanual-eip/eip_0007.html)。

        -   暂不使用：若新增节点未绑定弹性IP，则在该节点上运行的工作负载将不能被外网访问，仅可作为私有网络中部署业务或者集群所需云服务器进行使用。
        -   自动创建：选中后将根据您的配置购买弹性IP，并自动为每个节点进行分配。当购买的弹性IP数量小于节点个数时，会将弹性IP随机绑定到节点上。

            请根据业务需求和界面提示，选择弹性IP的规格、计费模式、带宽类型、带宽大小等。创建弹性云服务器时，请确保弹性IP配额充足。

        -   使用已有：请选择已有的弹性IP，将为当前节点分配已有弹性IP。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >CCE默认不启用VPC的SNAT。若VPC启用了SNAT，可以不使用EIP去访问外网。SNAT具体请参见[自定义策略](集群权限（IAM授权）.md#section1437818291149)。

    -   **共享带宽：**请选择“暂不使用”或“使用已有”。**仅在集群开启IPv6时，显示该参数。**

        弹性公网IP提供外网访问能力，可以灵活绑定及解绑，随时修改带宽。未绑定弹性公网IP的云服务器无法直接访问外网，无法直接对外进行互相通信。

    -   **登录方式：**支持密码和密钥对。
        -   选择“密码“：用户名默认为“root”，请输入登录节点的密码，并确认密码。

            登录节点时需要使用该密码，请妥善管理密码，系统无法获取您设置的密码内容。

        -   选择“密钥对“：选择用于登录本节点的密钥对，支持选择共享密钥。

            密钥对用于远程登录节点时的身份认证。若没有密钥对，可单击选项框右侧的“创建密钥对”来新建，创建密钥对操作步骤请参见[创建密钥对](https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0014250631.html)。

            >![](public_sys-resources/icon-notice.gif) **须知：** 
            >如果子用户创建节点选择密钥对创建，这个密钥只对创建这个密钥的子用户有效，即使其他子用户在同一个组也无法选择，也无法使用。例如：A用户创建的密钥，B用户无法使用这个密钥对创建节点，并且Console也选不到。

            **图 5**  密钥对<a name="fig82271742193213"></a>  
            ![](figures/密钥对.png "密钥对")

    -   **云服务器高级设置：**（可选），单击![](figures/zh-cn_image_0183134608.png)展开后可对节点进行如下高级功能配置：
        -   **云服务器组：**云服务器组是对云服务器的一种逻辑划分，同一云服务器组中的云服务器遵从同一策略。

            -   反亲和性策略：同一云服务器组中的云服务器分散地创建在不同主机上，提高业务的可靠性。
            -   故障域策略：同一云服务器组中分布多个故障域，指定不同故障域可以实现云服务器的故障隔离，提高业务的可靠性。当环境支持故障域时，才会显示该选项。随机可用区不支持故障域策略。

            选择已创建的云服务器组，或单击“新建云服务器组“创建，创建完成后单击刷新按钮。

        -   **资源标签：**通过为资源添加标签，可以对资源进行自定义标记，实现资源的分类。

            您可以在TMS中创建“预定义标签“，预定义标签对所有支持标签功能的服务资源可见，通过使用预定义标签可以提升标签创建和迁移效率。具体请参见[创建预定义标签](https://support.huaweicloud.com/usermanual-tms/zh-cn_topic_0144368884.html)。

            CCE服务会自动帮您创建CCE-Dynamic-Provisioning-Node=节点id的标签，允许增加5个标签。

        -   **委托：**委托是由租户管理员在统一身份认证服务上创建的。通过委托，可以将云主机资源共享给其他帐号，或委托更专业的人或团队来代为管理。新建委托请参见[委托其他云服务管理资源](https://support.huaweicloud.com/usermanual-iam/iam_06_0004.html)，创建委托时委托类型选择“云服务“，单击“选择“按钮并在弹出的窗口中选择“ECS BMS“，即允许ECS或BMS调用云服务。
        -   **安装前执行脚本：**请输入脚本命令，大小限制为0\~1000字符。

            脚本将在Kubernetes软件安装前执行，可能导致Kubernetes软件无法正常安装，需谨慎使用。常用于格式化数据盘等场景。

        -   **安装后执行脚本：**请输入脚本命令，大小限制为0\~1000字符。

            脚本将在Kubernetes软件安装后执行，不影响Kubernetes软件安装。常用于修改Docker配置参数等场景。

        -   **子网IP：**可选择“自动分配IP地址“和“手动分配IP地址“，推荐使用“自动分配IP地址“。

    -   **Kubernetes高级设置：**（可选），单击![](figures/zh-cn_image_0183134479.png)展开后可对集群进行如下高级功能配置：
        -   **最大实例数：**节点最大允许创建的实例数\(Pod\)，该数量包含系统默认实例。集群网络模型为“VPC网络“时，此处的最大值取决于您选择的每个节点可供分配的容器IP个数。

            该设置的目的为防止节点因管理过多实例而负载过重，请根据您的业务需要进行设置。

        -   **单容器可用数据空间：**该参数用于设置一个容器可用的数据空间大小，设置范围为10G到80G。如果设置的参数超过数据盘中Docker可占用的实际数据空间（由数据盘设置项中的资源分配自定义参数指定，默认为数据盘大小的90%），将以Docker的实际空间大小为主。该参数仅在v1.13.10-r0及以上版本的集群中显示。

    -   **节点购买数量：**此处设置的节点数不能超过集群管理的最大节点规模，请根据业务需求和界面提示进行选择，单击后方的![](figures/zh-cn_image_0250508826.png)可查看影响能添加节点数的因素（取决于最小值）。如需申请更多配额，请单击[申请扩大配额](https://console.huaweicloud.com/quota/?locale=zh-cn#/quota)。
    -   **购买时长：**若选择创建“包年/包月“的集群，请设置购买时长。

4.  单击“下一步：安装插件“，在“安装插件“步骤中选择要安装的插件。

    “系统资源插件“为必装插件，“高级功能插件“可根据实际需求进行选择性安装。

    所有插件也可以在集群创建完成后，在左侧导航栏中单击“插件管理“进行安装或卸载，具体请参见[插件管理](插件管理.md)  。

5.  单击“下一步：配置确认”，阅读“使用说明“并点选“我已知晓上述限制“，确认所设置的服务选型参数、规格和费用等信息。
6.  确认规格和费用后，单击“提交”，集群开始创建。

    若选择购买“包年包月“的集群，请单击“去支付“，根据界面提示进行付款操作。

    集群创建预计需要6-10分钟，您可以单击“返回集群管理“进行其他操作或单击“查看集群事件列表“后查看集群详情。待集群状态为“正常”，表示集群创建成功。


## 相关操作<a name="section125261255139"></a>

-   通过命令行工具连接集群：请参见[通过kubectl连接集群](通过kubectl连接集群.md)。
-   添加节点：集群创建完成后，若您需要为集群添加更多节点，请参见[购买节点](购买节点.md)。
-   登录节点：请参见[登录节点](登录节点.md)。

-   创建命名空间：同个集群内可创建多个命名空间，形成逻辑上的不同分组，便于不同的分组在共享使用集群资源时还能被分别管理。若您需要为集群创建命名空间，请参见[命名空间](命名空间.md)。
-   创建工作负载：集群创建完成后，您可以使用镜像创建一个可公网访问的应用，请参见[创建无状态负载\(Deployment\)](创建无状态负载(Deployment).md)或[创建有状态负载\(StatefulSet\)](创建有状态负载(StatefulSet).md)。
-   单击已成功创建的集群名称，进入“集群详情“页可查看集群详情。

    **表 2**  已创建的集群详情

    <a name="table1642185503514"></a>
    <table><thead align="left"><tr id="row1264365516359"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.3.1.1"><p id="p76431955153512"><a name="p76431955153512"></a><a name="p76431955153512"></a>页签类别</p>
    </th>
    <th class="cellrowborder" valign="top" width="80%" id="mcps1.2.3.1.2"><p id="p176431155163517"><a name="p176431155163517"></a><a name="p176431155163517"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row5975069716956"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p796825616956"><a name="p796825616956"></a><a name="p796825616956"></a>集群详情</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p4144902016956"><a name="p4144902016956"></a><a name="p4144902016956"></a>可查看该集群的详情及运行状态等。</p>
    </td>
    </tr>
    <tr id="row106431055133510"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1364315552359"><a name="p1364315552359"></a><a name="p1364315552359"></a>监控</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p5583863516649"><a name="p5583863516649"></a><a name="p5583863516649"></a>可查看集群下全部节点的CPU和内存分配率（即分配量的最大值），以及控制节点的CPU和内存使用率、控制节点规格等信息。</p>
    </td>
    </tr>
    <tr id="row1464335593515"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1264365518351"><a name="p1264365518351"></a><a name="p1264365518351"></a>事件</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><a name="ul42186174161243"></a><a name="ul42186174161243"></a><ul id="ul42186174161243"><li>可以直接在“事件”页签下查看集群的事件。</li><li>可以设置查询条件，比如设置事件产生的时间段或搜索事件名称，查看相关事件。</li></ul>
    </td>
    </tr>
    <tr id="row506129238"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p160812132312"><a name="p160812132312"></a><a name="p160812132312"></a>弹性扩容</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p90512182317"><a name="p90512182317"></a><a name="p90512182317"></a>您可以根据实际业务需要对集群的工作节点进行扩容和缩容，详情请参见<a href="集群弹性扩容.md">集群弹性扩容</a>。</p>
    <p id="p218234511328"><a name="p218234511328"></a><a name="p218234511328"></a>v1.17版本的集群不再支持AOM提供的弹性伸缩机制，请使用节点池功能进行弹性伸缩，详情请参见<a href="节点池概述.md">节点池概述</a>。</p>
    </td>
    </tr>
    <tr id="row651036112414"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1251015692419"><a name="p1251015692419"></a><a name="p1251015692419"></a>kubectl</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p35101368242"><a name="p35101368242"></a><a name="p35101368242"></a>若您需要从客户端计算机连接到kubernetes集群，请使用kubernetes命令行客户端<a href="https://kubernetes.io/docs/user-guide/kubectl/" target="_blank" rel="noopener noreferrer">kubectl</a>，详情请参见<a href="通过kubectl连接集群.md">通过kubectl连接集群</a>。</p>
    </td>
    </tr>
    <tr id="row1442823812251"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p96289022317"><a name="p96289022317"></a><a name="p96289022317"></a>资源标签</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p11774125042315"><a name="p11774125042315"></a><a name="p11774125042315"></a>通过为资源添加标签，可以对资源进行自定义标记，实现资源的分类。</p>
    <p id="p177435013232"><a name="p177435013232"></a><a name="p177435013232"></a>您可以在TMS中创建<span class="uicontrol" id="uicontrol7775105022310"><a name="uicontrol7775105022310"></a><a name="uicontrol7775105022310"></a>“预定义标签”</span>，预定义标签对所有支持标签功能的服务资源可见，通过使用预定义标签可以提升标签创建和迁移效率。具体请参见<a href="https://support.huaweicloud.com/usermanual-tms/zh-cn_topic_0144368884.html" target="_blank" rel="noopener noreferrer">创建预定义标签</a>。</p>
    <p id="p15775125014232"><a name="p15775125014232"></a><a name="p15775125014232"></a>CCE服务会自动帮您创建CCE-Dynamic-Provisioning-Node=节点id的标签，允许增加5个标签。</p>
    </td>
    </tr>
    <tr id="row2701721182419"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p6701721122417"><a name="p6701721122417"></a><a name="p6701721122417"></a>Istioctl</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p1701821112418"><a name="p1701821112418"></a><a name="p1701821112418"></a>在集群开启istio服务网格功能后，您使用Istio命令行工具Istioctl配置多种路由策略，从而管理服务流量，包括流量转移、故障注入、限流熔断等。详情请参见<a href="启用istio.md">启用istio</a>。</p>
    </td>
    </tr>
    </tbody>
    </table>


