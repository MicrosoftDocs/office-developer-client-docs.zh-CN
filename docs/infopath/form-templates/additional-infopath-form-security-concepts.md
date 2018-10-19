---
title: 更多 InfoPath 表单安全性概念
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 77425a61-bf33-b3d8-442a-caee48e54a48
description: Microsoft InfoPath 安全模型基于 Internet Explorer 实现的安全模型。Internet Explorer 安全模型可使用安全区域和级别来帮助保护计算机免受不安全操作的危害。通过与 Internet Explorer 安全模型协同工作，InfoPath 可提供两种类型的表单部署，这些部署将影响 InfoPath 表单在此安全模型中的工作方式。
ms.openlocfilehash: 00b0e306507db19f55059fba91277af1ad1714b9
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25387417"
---
# <a name="additional-infopath-form-security-concepts"></a>更多 InfoPath 表单安全性概念

Microsoft InfoPath 安全模型基于 Internet Explorer 实现的安全模型。Internet Explorer 安全模型可使用安全区域和级别来帮助保护计算机免受不安全操作的危害。通过与 Internet Explorer 安全模型协同工作，InfoPath 可提供两种类型的表单部署，这些部署将影响 InfoPath 表单在此安全模型中的工作方式。
  
- **基于 URL 的表单** ：此部署方法是在将 InfoPath 表单发布到 Web 服务器、SharePoint Foundation 表单库或文件共享时使用的默认方法。这些表单之所以称为基于 URL 的表单是因为，用户通常从发布表单的 URL 处打开表单，该 URL 在表单定义文件 (.xsf) 中的 **xDocumentClass** 元素的 **publishUrl** 属性中指定。基于 URL 的表单就是所谓的 沙盒表单，因为这些表单只能对系统资源和其他可能的风险区域进行受限访问。基于 URL 的表单与从同一位置作为表单模板文件 (.xsn) 打开的网页具有相同的权限级别。
    
- **基于 URN 的表单** ：此部署方法针对需要访问系统资源和其他外部资源（例如 ActiveX 控件和其他软件组件）的表单。您可以将 InfoPath 表单部署为完全信任的表单。此类表单也称为 基于 URN 的表单，因为这些表单不指定 **publishUrl** 属性，而是在表单定义文件 (.xsf) 中 **xDocumentClass** 元素的 **name** 属性中指定统一资源名称 (URN)。如果 **xDocumentClass** 元素的 **requireFullTrust** 属性在表单定义文件 (.xsf) 中设置为  `"yes"`，则此类表单可请求完全信任。基于 URN 的表单必须由安装程序或脚本在客户端计算机上注册。在这种情况下，该表单将获得与在本地计算机上运行的应用程序相同的权限。 
    
通过将这两种表单部署方法结合使用，InfoPath 对象模型中的每种方法和属性都将具有相应安全级别，以控制何时可以通过在表单中运行的脚本调用该方法或属性。
  
## <a name="understanding-infopath-integration-with-the-internet-explorer-security-model"></a>了解 InfoPath 与 Internet Explorer 安全模型的集成

Internet Explorer 实现了安全区域，这使您能够控制所打开的网页为您的计算机提供的访问级别。InfoPath 使用其中某些区域来确定为表单提供的对计算机上资源的访问级别。默认情况下，InfoPath 表单在拒绝访问关键系统资源的缓存位置运行。允许完全访问系统资源的表单称为完全信任的表单。通常使用安装程序或脚本来安装和注册完全信任的表单，或对这些表单进行数字签名以便可为其授予更高级别的权限。
  
InfoPath 缓存表单由该表单的表单定义文件 (.xsf) 中指定的 URL 或 URN 来标识。使用的标识种类以及从中打开表单模板的域（位置）确定表单将继承哪些 Internet Explorer 安全区域权限。由 URL 标识的表单将缓存到可脱机使用表单的用户计算机。这些基于 URL 的表单通过适用于表单模板原始位置的 Internet Explorer 安全设置继承其安全权限和特定访问权限（如跨域访问权限）。存储在 Web 服务器上或运行 SharePoint Foundation 的服务器上的表单模板在 Internet 上或本地 Intranet 区域运行，具体取决于服务器所在的域。另一方面，由 URN 标识的已安装表单从本地计算机区域继承其权限，该区域所授予的权限级别类似于为 HTML 应用程序文件 (.hta) 授予的权限级别。
  
完全受信任的表单由其 URN 和表单定义 (.xsf) 文件中 **xDocumentClass** 元素的 **requireFullTrust** 属性是否设置为 `"yes"` 标识。 在 InfoPath 中，安装完全受信任的表单后，它们将显示在 InfoPath 编辑器的 Microsoft Office Backstage 的“新建”**** 选项卡上。 
  
有关完全信任的表单的工作方式以及如何创建和部署这些表单的详细讨论，请参阅[了解完全信任的表单](understanding-fully-trusted-forms.md)。
  
## <a name="trusting-installed-forms"></a>信任已安装表单

可以在单个计算机上允许或禁止使用信任表单。当计算机配置为信任已安装的表单时，用户则可以填写需要访问其计算机资源的表单。
  
在 InfoPath 编辑器中，可以在 Backstage 中将计算机配置为信任已安装的表单，方法是依次单击“选项”****、“信任中心”**** 和“信任中心设置”****，然后选中“信任中心”**** 对话框中“受信任的发布者”**** 选项卡上的“允许完全信任的表单在我的计算机上运行”**** 复选框。 
  
## <a name="using-security-features-in-infopath"></a>使用 InfoPath 中的安全功能

InfoPath 安全模型可帮助用户抵御恶意创建的模板造成的以下威胁：
  
- 可能公开您的本地计算机或远程数据源中的敏感信息。
    
- 恶意使用 ActiveX 控件。
    
- 恶意使用 InfoPath 对象模型中的属性和方法。
    
## <a name="cross-domain-data-access"></a>跨域数据访问

跨域数据访问 是一种安全风险。
  
基于其构建 InfoPath 的 Internet Explorer 安全模型提供称为“跨域访问数据源”**** 的设置。 默认情况下，此设置禁用驻留在 Internet 和受限制站点安全区域中的 InfoPath 表单的跨域访问。 此设置还会提示用户为驻留在本地 Intranet 安全区域的 InfoPath 表单允许或禁止跨域访问，并且为驻留在“可信站点”**** 或“本地计算机”**** 区域的 InfoPath 表单启用跨域访问。 
  
## <a name="use-of-the-infopath-html-task-pane"></a>使用 InfoPath HTML 任务窗格

InfoPath HTML 任务窗格能够呈现网页，例如 .htm, .asp 和 .hta 文件。从任务窗格引用的网页可位于表单模板之内或之外。对可从表单模板之外引用的网页的唯一限制是，该网页必须与表单模板位于同一域中，或者模板所在的安全区域必须允许跨域访问权限以加载任务窗格。
  
任务窗格不会显示地址栏或状态栏，因此用户无法确认任务窗格的源位置，也无法确认是否正通过加密通道 (https) 访问该位置。鉴于此原因，应避免使用任务窗格显示或输入敏感信息。任务窗格设计用于显示动态帮助信息以及用于在集成解决方案的各视图和其他元素之间导航的控件。另外，表单模板的业务逻辑和任务窗格中的脚本可以彼此交互。但是，仅当表单模板和任务窗格在同一域中时，才允许进行此交互，这将有助于防止跨域交换信息。
  
## <a name="cross-domain-data-access-prompts"></a>跨域数据访问提示

如果需要跨域数据访问的表单模板所在的安全区域设置为提示是否允许进行跨域数据访问（本地 Intranet 区域的默认设置），则系统将提示用户是否允许进行访问。然后，在打开表单后的剩余时间内，用户的选择将始终有效。如果您必须部署需要跨域数据访问的 InfoPath 表单模板，则应该将这些模板部署为完全信任的表单，或使其能够用于位于受信任站点安全区域中的服务器，以避免提示用户允许访问。为避免出现这些提示，不应指示用户降低本地 Intranet 区域的安全级别。
  
## <a name="forms-without-a-publishurl-attribute"></a>不带 publishURL 属性的表单

如果 InfoPath 从本地计算机加载表单模板并且它具有空白的 **publishUrl** 属性或缺少该属性，则表单将被放置在更严格的安全区域中。 执行此操作是为了减少通过电子邮件分发的恶意表单模板的威胁。 因此，如果用户将此表单模板保存到磁盘，将无法使用驻留在**本地计算机**区域中的表单的权限运行。 
  
## <a name="unsafe-activex-controls"></a>不安全的 ActiveX 控件

如果作者将脚本与 ActiveX 控件结合使用，以提供用于访问文件系统的方法，来检索个人文件和密码列表，从而删除文件或者禁用用户的系统，则可能发生恶意使用 ActiveX 控件的最常见情况。InfoPath 表单只能通过表单 (script.js) 的主脚本文件中的脚本或任务窗格中的脚本来使用 ActiveX 控件。InfoPath 不允许 InfoPath 视图中的脚本运行 ActiveX 控件。
  
作为 Microsoft InfoPath 构建基础的 Internet Explorer 安全模型还提供了一项称为“对标记为不安全的 ActiveX 控件进行初始化和脚本运行”**** 的设置。默认情况下，该设置会导致针对 InfoPath 表单或任务窗格执行以下操作，从而尝试对没有标记为可安全运行脚本的 ActiveX 控件进行初始化和脚本运行。 
  
|**安全区域/部署**|**操作**|
|:-----|:-----|
|Internet  <br/> |已禁用  <br/> |
|本地 intranet  <br/> |已禁用  <br/> |
|受限制的站点  <br/> |已禁用  <br/> |
|受信任网站  <br/> |提示  <br/> |
|我的电脑  <br/> |提示  <br/> |
|完全信任的表单  <br/> |启用  <br/> |
   
## <a name="malicious-use-of-the-infopath-object-model"></a>InfoPath 对象模型的恶意使用

与从脚本调用的 ActiveX 控件类似，从代码调用的 InfoPath 方法和属性也会带来不同级别的风险。例如，[XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.SaveAs.aspx) 类的 [SaveAs(String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 方法可用于在文件系统中的任意位置写入数据。 
  
为防止恶意使用 InfoPath 对象模型成员，InfoPath 对象模型实现了三种安全级别，以确定可以使用特定对象模型成员的方式和位置。InfoPath 对象模型中有三种安全级别：
  
- **0** 可以无限制访问的对象模型成员。这些对象模型成员是安全的，因此可以无限制地访问它们。 
    
- **2** 只能由当前打开的表单所在域中运行的表单或者已授予跨域数据访问权限的表单访问的对象模型成员。仅当调用安全级别 2 对象模型方法的受限制的表单模板访问表单模板本身中包含的资源时，这些模板才会成功。 
    
- **3** 只能由完全信任的表单访问的对象模型成员。 
    
- InfoPath 对象模型引用中属性和方法的每个主题都包含一个安全部分，该部分指定适用于该对象模型成员的安全级别。
    
- 安全级别 **1** 保留供以后使用。 
    
## <a name="summary"></a>摘要

下表总结了 InfoPath 中每个表单部署方法的默认权限。这些权限基于源自其中的表单模板的域的安全区域。
  
|**安全区域**|**部署**|**默认权限**|
|:-----|:-----|:-----|
||**基于 URL** <br/> |**基于 URN** <br/> |**将脚本标记为不安全的 ActiveX** <br/> |**跨域数据访问** <br/> |**对象模型安全级别** <br/> |
|受限站点  <br/> |不适用  <br/> |不适用  <br/> |不适用  <br/> |不适用  <br/> |不适用  <br/> |
|Internet  <br/> |X  <br/> ||禁用  <br/> |禁用  <br/> |2  <br/> |
|本地 intranet  <br/> |X  <br/> ||禁用  <br/> |提示  <br/> |2  <br/> |
|受信任网站  <br/> |X  <br/> ||提示  <br/> |启用  <br/> |2  <br/> |
|本地计算机  <br/> |X  <br/> |X  <br/> |禁用  <br/> |提示  <br/> |2  <br/> |
|完全信任的表单  <br/> |X（经受信任的发布者签名）  <br/> |X  <br/> |启用  <br/> |启用  <br/> |3  <br/> |
|完全信任的表单  <br/> ||X  <br/> |启用  <br/> |启用  <br/> |3  <br/> |
|受限  <br/> ||X  <br/> |无 ActiveX（除受限制的硬编码列表外）  <br/> |禁用  <br/> |2  <br/> |
|受限  <br/> |X  <br/> ||无 ActiveX（除受限制的硬编码列表外）  <br/> |禁用  <br/> |2  <br/> |
|受限  <br/> |X  <br/> |X  <br/> |无 ActiveX（除受限制的硬编码列表外）  <br/> |禁用  <br/> |2  <br/> |
   
有关开发表单时使用的一般安全指南的信息，请参阅[开发 InfoPath 表单的安全指南](security-guidelines-for-developing-infopath-forms.md)。
  
## <a name="understanding-other-security-features"></a>了解其他安全功能

InfoPath 为表单提供的其他安全措施包括使用数字签名保护表单设计、管理特定表单操作（如合并和提交）以及信任已安装的表单。下面各节介绍这些表单安全措施以及在 InfoPath 中启用这些措施的位置。
  
## <a name="digital-signatures"></a>数字签名

可以对表单中包含的数据进行数字签名，以帮助确保数据内容不会被更改。
  
你可以通过选择“表单选项”**** 对话框的“数字签名”**** 部分中的“允许对整个表单进行签名”**** 或“允许对表单的某些部分进行签名”**** 选项来配置表单以使用数字签名，该对话框可在 InfoPath 表单设计器中的 Microsoft Office Backstage 中找到。 填写表单时，用户可以通过单击 Microsoft Office Backstage 的“信息”**** 选项卡上的“签名表单”**** 按钮来签名和验证表单。 当再次打开表单时，如果表单的内容已被更改，系统将提醒用户。 
  
-  可以对整个表单进行数字签名，也可以对表单中可单独签名的特定数据集进行数字签名。 
    
- 可以选择只签署表单的特定部分，而不是签署整个表单。
    
- 您可以指定允许单个还是多个签名，还可以指定可以签署的每个数据集之间的关系。例如，可以指定它们是否是并行联署，以及每个新的签名是否都副署所有更早的签名。
    
- 可以使用 InfoPath 对象模型以编程方式将自定义信息添加到完全信任的表单中的签名块。
    
- 通过捕获额外信息（如时间戳）并将其作为不可否认性证据，可以提高数字签名的安全性。由于此额外证据是签名的一部分，因此在签名没有失效的情况下不能将其删除。通过单击表单中的数字签名，或从“数字签名”**** 对话框中显示的数字签名列表中选择数字签名，您可以随时重新调用或检查捕获的数据。 
    
-  可以插入并查看文档中的签名，并按照呈现给每个签名人的方式查看表单。 
    
- 数字签名还包含签署表单后呈现给签名人的签名视图的快照。该快照以标准 PNG 文件格式存储为 base64 编码的图像。 
    
## <a name="email-deployment"></a>电子邮件部署

你可以将表单模板部署为电子邮件的附件并将表单模板从一个位置移到另一个位置。 邮件部署是一种简单有效的分发表单以供局间使用及将表单部署到远程用户的方式。
  
你可以对你设计的表单模板进行数字签名，然后将该表单模板的安全级别设置为完全信任。 此外，如果将已签名的完全信任的表单部署为电子邮件附件，则可以更加轻松高效地对这些表单进行更新。
  
在 InfoPath Designer 中创建的所有表单都具有标识。 此信息可帮助 InfoPath 将表单与缓存中的表单模板相关联，而且当表单发布到共享位置时，还可帮助检索对表单的更新。 默认情况下，InfoPath 为表单模板创建两个标识：表单 ID 和访问路径（也称为 **publishURL** 属性）。 可在[安全级别、电子邮件部署和远程表单模板](security-levels-email-deployment-and-remote-form-templates.md)主题中查找有关电子邮件部署的详细信息。
  
## <a name="activex-controls"></a>ActiveX 控件

InfoPath 支持在使用 InfoPath 编辑器打开的表单中托管 ActiveX 控件。这些 ActiveX 控件可以是现成的（具有某些约束），也可以是为了与 InfoPath 配合使用而专门编写的。InfoPath 表单中使用的 ActiveX 控件不会从网站自动下载。相反，必须将用户计算机上尚无的 ActiveX 控件的 CAB 文件添加到表单模板文件中。
  
当在表单中使用 ActiveX 控件并且未在用户计算机上注册该控件，则打开表单时的行为将取决于该表单中 ActiveX 控件的设置。如果表单模板文件中未包含任何 CAB 文件，则 InfoPath 将不打开该表单。如果表单模板文件中包含 CAB 文件，则 InfoPath 将启动安装过程。为使 InfoPath 能够安装 CAB 文件，必须签署该文件，并且签名必须来自受信任的发布者。如果该发布者不在用户具有证书（包含指向受信任的证书根目录的信任链）的受信任的发布者列表中，则系统将提示用户是接受还是拒绝信任该发布者。如果用户选择不信任该发布者，则不会安装该控件的 CAB 文件，而且 InfoPath 不会打开该表单。
  
> [!NOTE]
> ActiveX 控件必须标记为"可安全编写脚本"和"可安全使用不受信任的数据进行初始化"才能在 InfoPath 中使用。 
  
## <a name="net-security"></a>.NET 安全

托管代码表单模板除了支持 InfoPath 特定的安全级别外，还支持其他代码访问安全功能，这些功能适用于在 Microsoft .NET Framework 的公共语言运行库 (CLR) 下运行的托管代码。
  
如果您的表单是完全信任的表单，则该表单可自动访问表单模板外部的资源。任何程序集都可用于业务逻辑代码。您可以使用 Microsoft .NET Framework 配置工具或代码访问安全策略工具 (Caspol.exe) 自定义添加到托管代码表单模板中的权限集。InfoPath 将查找预定义的代码组并将在该组下定义的权限集应用到应用程序域 (AppDomain)（这是在其中加载托管代码并从中运行该代码的位置）。必须将自定义 .NET 安全策略部署到将在其中运行该托管代码表单模板的客户端计算机。
  
请注意，.NET 安全仅向在 Internet Explorer 受信任的站点中运行的托管代码授予 Internet 权限集。因此，如果将 InfoPath 托管代码表单发布到受信任的站点，这些表单将不会运行。
  
## <a name="merging-forms"></a>合并表单

您可以禁用表单合并功能，以防止用户将数据从多个表单导入一个表单中。
  
可以使用“表单选项”**** 对话框的“高级”**** 部分中的“启用表单合并”**** 复选框启用或禁用表单合并，该对话框可在设计表单时从 Microsoft Office Backstage 的“信息”**** 选项卡中找到。 禁用表单合并时，用户在填写表单时无法单击 Microsoft Office Backstage 的“共享”**** 选项卡上的“合并表单”****。 
  
## <a name="submitting-forms"></a>提交表单

您可以禁用表单提交功能，以防止用户提交表单。
  
可通过“提交选项”**** 对话框（在设计模式中单击“数据”**** 选项卡菜单上的“提交选项”****）来启用或禁用表单提交功能。禁用表单提交时，用户将无法在填写表单时单击“开始”**** 选项卡上的“提交”****。 
  

