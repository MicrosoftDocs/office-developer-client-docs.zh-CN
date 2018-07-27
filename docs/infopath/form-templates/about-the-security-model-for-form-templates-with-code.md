---
title: 关于具有代码的表单模板的安全模型
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- infopath 2007, security,code access security [InfoPath 2007],security [InfoPath 2007], security model for managed code,security [InfoPath 2007], levels,CAS [InfoPath 2007],InfoPath 2003-compatible form templates, security,permissions [InfoPath 2007]
localization_priority: Normal
ms.assetid: 5e1c1c72-f98d-4871-9c57-82c315277aa1
description: InfoPath 托管代码表单模板与非托管表单模板中运行的脚本支持相同的安全级别，它们还支持适用于 .NET Framework 公共语言运行库 (CLR) 下运行的托管代码的其他代码访问安全功能。
ms.openlocfilehash: cfeb2117232d041cef43d282ff5aab482609f512
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773969"
---
# <a name="about-the-security-model-for-form-templates-with-code"></a>关于具有代码的表单模板的安全模型

InfoPath 托管代码表单模板与非托管表单模板中运行的脚本支持相同的安全级别，它们还支持适用于 .NET Framework 公共语言运行库 (CLR) 下运行的托管代码的其他代码访问安全功能。
  
## <a name="infopath-managed-object-model-security-levels"></a>InfoPath 托管对象模型安全级别

下表说明脚本对象模型成员的安全级别与在托管代码表单模板中使用对象模型成员时每个级别所需的相应权限集之间的关系。
  
|**对象模型安全级别**|**说明**|**所需的权限集**|
|:-----|:-----|:-----|
|0  <br/> |可以无限制访问。  <br/> |无  <br/> |
|2  <br/> |只能由与当前打开的表单运行在相同域中的表单或者已被授予跨域权限的表单访问。  <br/> |无  <br/> |
|3  <br/> |只能由完全受信任的表单访问。  <br/> |FullTrust  <br/> |
   
> [!NOTE]
> 安全级别"1"未由当前 InfoPath COM 服务器使用，而是保留以供将来使用。 
  
> [!IMPORTANT]
> 虽然对象模型级别 0 和 2 不需要任何权限集，但由于它们包含托管代码，它们的行为将与为 Domain 域访问安全级别（下一节对此进行了说明）定义的行为相同。 
  
由 Microsoft.Office.InfoPath 和 Microsoft.Office.Interop.InfoPath.SemiTrust 程序集公开的每个对象模型成员的安全级别，在介绍 [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 和 [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 命名空间中该成员的主题的"备注"一节指定。 
  
## <a name="infopath-domain-access-security-levels"></a>InfoPath 域访问安全级别

连同由 InfoPath 应用程序公开的 COM 服务器强制执行的对象模型安全级别，InfoPath 定义了三个安全级别，其应用情况取决于表单模板的位置、表单的部署方式以及设计模式中配置的设置。下表对这三个安全级别进行了定义。
  
|**域访问安全级别**|**说明**|
|:-----|:-----|
|受限  <br/> |不允许在表单模板外进行任何通信。 此安全级别旨在防止有害的表单将任何数据从计算机传输到恶意攻击者。 在此安全模式下运行时，下列功能将无法工作：自定义任务窗格、数据连接（电子邮件提交除外）、ActiveX 控件、托管代码表单代码、角色和工作流。 无法在受限制的域中运行托管代码表单模板。 将托管代码表单模板设置为“表单选项”**** 对话框的“安全和信任”**** 类别中的“自动确定安全级别”**** 时，表单模板将始终需要至少域安全访问级别才能运行代码。  <br/><br/>**重要说明**：从受限制的域打开表单时（例如从作为电子邮件附件发送的 InfoPath 表单打开），为托管代码表单模板创建的托管代码程序集将不会加载或运行。 想要以电子邮件附件形式部署任何表单模板则必须省略以上列出的功能，且如果表单模板包含表单代码，则必须在 JScript 或 VBScript 中执行表单代码并且必须只使用安全级别为 0（零）的对象模型成员。           |
|域  <br/> |根据表单在由 Microsoft Internet Explorer 定义的其中某个安全区域的位置来限制表单。例如，如果表单位于"本地 Intranet"区域，则允许表单与它所在域中的其他数据进行通信，但不允许从其他域中检索数据。Microsoft Internet Explorer 安全区域中的位置还将决定是否允许运行对脚本标记为不安全的 ActiveX 控件。  <br/> |
|完全信任  <br/> |允许在将要使用表单的计算机上以完全信任方式运行表单。仅当对所用表单进行数字签名的签名与计算机上受信任的根发布者匹配时，或当创建的安装程序安装表单并在表单定义文件 (.xsf) 中将 **xDocumentClass** 元素的 **requireFullTrust** 属性设置为"yes"时，才能使用此安全级别。通过使用此设置，您的表单可以访问需要对象模型安全级别 3 的对象模型调用，例如，访问文件系统的属性和方法，您可以禁用在更严格的安全级别运行时出现的某些安全提示。  <br/> |
   
默认情况下，InfoPath 表单配置为自动选择"受限"安全级别或"域"安全级别，具体取决于在表单模板中使用的功能以及表单模板的部署位置和部署方式。 例如，以电子邮件附件形式部署的表单模板将自动配置为“受限”安全级别。 安全设置始终是尽量严格（从"受限"开始），以确保对您和您的数据提供更高级别的保护。 将包含托管代码的表单模板设置为自动选择安全级别时，该表单模板将始终至少需要"域"安全访问级别才能运行代码。 您可以使用以下过程在设计时手动覆盖此设置，以选择更适合该表单的安全级别。 
  
### <a name="specify-a-forms-security-level"></a>指定表单的安全级别

1. 在 InfoPath 表单设计器中打开表单，依次单击“文件”**** 选项卡、“信息”**** 和“表单选项”****。
    
2. 在“表单选项”**** 对话框中单击“安全和信任”**** 类别。 
    
3. 清除“自动确定安全级别(推荐)”**** 复选框。 
    
4. 选择需要的安全级别。
    
> [!NOTE] 
> - 如果为托管代码表单模板选择“受限”**** 安全级别，则无论表单代码中使用了哪些对象模型成员，都不会加载和运行表单背后的代码。 此安全级别主要针对使用电子邮件部署的 InfoPath 表单而设计。     
> - 如果选择“完全信任”**** 安全级别，则需要对表单进行数字签名或安装并注册表单。 有关详细信息，请参阅[部署具有代码的 InfoPath 表单模板](how-to-deploy-infopath-form-templates-with-code.md)。
    
下表总结了 InfoPath 安全模型。第一列列出为表单指定的级别或表单所需的级别。第二列和第三列指定表单的位置是具有 URN 还是 URL 标识符。剩余的列指定允许运行的内容。有关托管代码表单模板的部署方案和权限集的详细信息，请参阅本主题后面的"公共语言运行库代码访问安全功能"一节。
  
|**表单所需的级别**|**具有 URN 标识符**|**具有 URL 标识符**|**对脚本标记为不安全的 ActiveX**|**跨域访问**|**托管代码**|**对象模型安全**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|受限  <br/> ||X  <br/> |根本没有 ActiveX  <br/> |失败  <br/> |加载表单，但不运行托管代码  <br/> |0  <br/> |
|域（Internet Explorer **受限制的站点**区域）  <br/> |根本不运行  <br/> |根本不运行  <br/> |根本不运行  <br/> |根本不运行  <br/> |根本不运行  <br/> |根本不运行  <br/> |
|域（Internet Explorer **Internet** 区域）  <br/> |X  <br/> ||失败  <br/> |失败  <br/> |根本不运行  <br/> |0  <br/> |
|域（Internet Explorer **本地 Intranet** 区域）  <br/> |X  <br/> ||失败  <br/> |提示  <br/> |托管代码使用**本地 Intranet** 权限运行。  <br/> |2  <br/> |
|域（Internet Explorer **受信任的站点**区域）  <br/> |X  <br/> ||提示  <br/> |确定  <br/> |托管代码使用 **Internet** 权限运行。 允许跨域访问。 请注意，即使表单位于**受信任的站点**区域，也会应用 **Internet** 区域权限。  <br/> |2  <br/> |
|域（Internet Explorer **本地计算机**区域）  <br/> |X  <br/> |X  <br/> |提示  <br/> |失败  <br/> |托管代码使用**本地 Intranet** 权限运行。  <br/> |2  <br/> |
|完全信任  <br/> |X  <br/> |X  <br/> |确定  <br/> |确定  <br/> |完全信任  <br/> |3  <br/> |
   
> [!IMPORTANT]
> “将脚本标记为不安全的 ActiveX”和“跨域访问”列中的上述说明假定适用于 Microsoft Internet Explorer 的默认安全设置。 如果用户更改了他们的安全设置，InfoPath 将给出相应的表现。 例如，如果在**本地 Intranet** 区域中将“跨域访问数据源”**** 设置为“启用”****，则如表中所述，系统将不会提示用户允许跨域访问。 
  
## <a name="common-language-runtime-code-access-security-features"></a>公共语言运行库代码访问安全功能

编译 InfoPath 托管代码表单模板时，将创建一个包含表单代码逻辑实现的专用托管代码程序集。
  
在 .NET Framework 中，默认情况下，托管代码程序集在本地计算机上运行时具有"完全信任"权限，而在 Intranet 上运行时不被授予"完全信任"权限。为提供对安全策略更加细化的控制，并提供在 Intranet 中将 InfoPath 托管代码表单模板作为完全受信的表单运行的选项，InfoPath 实现了以下安全体系结构。
  
- InfoPath 应用程序承载 .NET Framework 公共语言运行库 (CLR)。
    
- 在由 InfoPath 承载的 CLR 内，每个托管代码表单模板都在单独的应用程序域中运行。应用程序域是一种为执行托管代码提供隔离、卸载和安全范围的环境。
    
- InfoPath 根据与表单模板及其位置的 URL 关联的信任级别来设置应用程序域的默认安全策略。
    
- 默认情况下，在本地计算机（"我的计算机区域"代码组）上运行的托管代码表单模板将获得低于"完全信任"（"本地 Intranet 区域"权限）的权限级别。要获得"完全信任"权限，必须注册表单或使用受信任的证书为其进行数字签名。
    
托管代码表单模板所在的应用程序域的默认安全策略集可确保强制执行 InfoPath 域访问安全级别以及任何其他 .NET 安全限制。若要提供更多灵活性，InfoPath 安全系统可识别名为"InfoPath 表单模板"的 .NET 代码访问安全代码组。如果此代码组存在于用户的计算机上，则该组的安全配置以及其所有子代码组的安全配置都将应用于应用程序域。
  
> [!IMPORTANT] 
> - InfoPath 表单模板代码组仅适用于托管代码表单代码程序集本身。因此，如果您对 InfoPath 托管代码表单代码授予"完全信任"权限集，但未安装和注册（或数字签名）表单模板本身（安装和注册表单模板或对表单模板进行数字签名可将整个表单模板设置为完全受信），则表单代码中对安全级别为 3 的对象模型成员的调用仍将失败。   
> - 即使您通过哈希、强名称或发布者证据引用或显式加载 (Assembly.Load) 使用受限权限集配置的程序集，以此来确定该程序集在表单模板项目中的成员资格条件，该表单模板仍将加载并执行该程序集。
    
有关如何创建和配置 InfoPath 表单模板代码组的信息，请参阅[为具有代码的表单模板配置安全设置](how-to-configure-security-settings-for-form-templates-with-code.md)。
  
下表汇总了应用于托管代码表单模板的部署方案和权限集。
  
|**部署方案**|**权限集**|**备注**|
|:-----|:-----|:-----|
|表单模板在本地计算机上发布，开发人员使用 Visual Studio 编写和调试表单代码。  <br/> |本地 Intranet 权限集。  <br/> 全局程序集缓存 (GAC) 中安装的程序集以及标记有 **AllowPartiallyTrustedCallersAttribute** 属性的程序集将被授予"完全信任"权限集。  <br/> |默认情况下，从本地计算机运行的表单模板未被授予完全信任权限集。 当要开发的表单模板使用需要“完全信任”权限的功能和对象模型成员调用时，可以使用[预览和调试需要完全信任的表单模板](how-to-preview-and-debug-form-templates-that-require-full-trust.md)中介绍的过程。  <br/> |
|表单模板在本地计算机上发布，并引用本地计算机上要求"完全信任"权限集的自定义程序集。  <br/> |本地 Intranet 权限集。  <br/> 全局程序集缓存 (GAC) 中安装的程序集以及标记有 **AllowPartiallyTrustedCallersAttribute** 属性的程序集将被授予"完全信任"权限集。自定义程序集将被授予"本地 Intranet"权限集。  <br/> |若要引用要在表单模板代码中使用的外部程序集，开发人员必须使用 InfoPath 表单模板代码组将"完全信任"（或适当的权限集）权限集授予表单模板代码中引用的外部程序集。InfoPath 不会进行任何有关外部程序集（安装在全局程序集缓存 (GAC) 中的外部程序集除外）的假设。开发人员必须使用 InfoPath 表单模板代码组向该程序集显式授予必需的权限，即使在该程序集已通过 My_Computer_Zone 代码组授予的权限变为可信时也不例外。  <br/> |
|表单模板在本地 Intranet 中的共享位置（例如，文件共享）、SharePoint 表单库或 Web 服务器上发布。  <br/> |本地 Intranet 权限集。  <br/> 全局程序集缓存 (GAC) 中安装的程序集以及标记有 **AllowPartiallyTrustedCallersAttribute** 属性的程序集将被授予"完全信任"权限集。  <br/> ||
|表单模板在本地 Intranet 中的共享位置（例如，文件共享）、SharePoint 表单库或指定为 Internet Explorer 中受信任站点的 Web 服务器上发布。  <br/> |Internet 权限集。  <br/> 经 Microsoft 和 ECMA 签名的程序集将被授予"完全信任"权限集。  <br/> |CLR 代码访问安全性仅向 Internet Explorer 中指定为"受信任的站点"的网站授予"Internet"权限集。InfoPath 将遵守此策略。请注意，它与在表单代码中使用脚本的 InfoPath 表单模板不同，当在"受信任的站点"区域中发布时，后者将收到更高的权限级别。  <br/> |
|表单模板从 Internet 位置下载或复制。  <br/> |无（默认情况）。将不加载和运行表单模板的托管代码程序集。  <br/> ||
   
## <a name="see-also"></a>另请参阅

- [为包含代码的表单模板配置安全设置](how-to-configure-security-settings-for-form-templates-with-code.md)
- [预览和调试需要完全信任的表单模板](how-to-preview-and-debug-form-templates-that-require-full-trust.md)

