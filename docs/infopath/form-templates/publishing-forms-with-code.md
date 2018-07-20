---
title: 发布包含代码的表单
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: caafab24-6413-4731-813d-cba3ae9ea97e
description: 任何网站集管理员都可以直接从 InfoPath Designer 发布向导中将包含代码的表单发布到 SharePoint 上的表单库。代码将在沙盒环境中执行，以使恶意代码无法损害服务器。这称为发布沙盒解决方案或发布到 SharePoint 沙盒基础结构。
ms.openlocfilehash: c25243a966bc1dc1a559ccf2ba58fabfadbd94a2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774090"
---
# <a name="publishing-forms-with-code"></a>发布包含代码的表单

任何网站集管理员都可以直接从 InfoPath Designer 发布向导中将包含代码的表单发布到 SharePoint 上的表单库。代码将在沙盒环境中执行，以使恶意代码无法损害服务器。这称为发布沙盒解决方案或发布到 SharePoint 沙盒基础结构。
  
InfoPath 2010 和 SharePoint Server 2010 也支持管理员部署的解决方案。表单设计人员将包含代码的表单发布到本地存储，SharePoint 服务器场管理员随后将审阅和上载这些表单。代码将被赋予完全信任，并可以结合需要提升的权限的功能（例如文件 IO）。
  
## <a name="comparing-sandboxed-and-administrator-approved-solutions"></a>比较沙盒解决方案和经管理员核准的解决方案

下表概述了发布沙盒解决方案和经管理员核准的解决方案之间的差异。 
  
||**沙盒解决方案**|**经管理员核准的解决方案**|
|:-----|:-----|:-----|
|**所需的权限** <br/> |可由任何网站集管理员发布。  <br/> |可由服务器场管理员部署。  <br/> |
|**Publishing** <br/> |可直接从 InfoPath 中发布。  <br/> |可使用管理中心或 stsadm 命令行工具部署。  <br/> |
|**保护** <br/> |代码运行于沙盒环境中。这可帮助保护服务器免受恶意代码的损害。  <br/> |代码能够以完全信任方式运行，并访问服务器上的任何资源。  <br/> |
|**建议的用途** <br/> |仅需要少量代码的表单。  <br/> |包含多行代码的表单。  <br/> |
   
### <a name="publishing-form-templates-as-sandboxed-solutions"></a>以沙盒解决方案的形式发布表单模板

以 沙盒解决方案 形式发布包含代码的表单与将任何其他表单发布到文档库没有不同之处。只需照常使用发布向导，您的表单即会上载到服务器并将在沙盒中运行。
  
请注意，以 沙盒解决方案 的形式部署表单有某些限制：
  
- 必须为 InfoPath 表单。
    
- 编程语言必须使用 C# 或 Visual Basic。
    
- 无法提交到电子邮件数据连接。
    
- 无法为部件与部件的连接提升属性。
    
- 不能有任何托管元数据控件或数据连接。
    
若要使网站集管理员能够在 Microsoft SharePoint Server 2010 或运行 Microsoft SharePoint Foundation 2010 的服务器上使用 沙盒解决方案，服务器场管理员必须启动 Windows SharePoint 用户代码服务。
  
### <a name="to-start-the-windows-sharepoint-user-code-service"></a>启动 Windows SharePoint 用户代码服务

1. 打开管理中心。
    
2. 在“**系统服务**”下，单击“**管理服务器上的服务**”。
    
3. 开启 **Microsoft SharePoint Foundation 用户代码服务**。
    
### <a name="to-publish-a-sandboxed-solution"></a>发布沙盒解决方案

1. 在 InfoPath 设计器中打开表单模板。
    
2. 单击“**文件**”选项卡，然后单击 Backstage 的“**发布**”选项卡上的“**SharePoint Server**”。 
    
3. 输入要将内容发布到的 SharePoint 站点的 URL ，然后单击“**下一步**”。 
    
    > [!IMPORTANT]
    > [!重要信息] 您必须是此网站上的网站集管理员才能以 沙盒解决方案 的形式发布此表单模板。 
  
4. 选择“**表单库**”，然后单击“**下一步**”。
    
5. 选择“**创建新的表单库**”，然后单击“**下一步**”。
    
6. 输入表单库的名称和描述，然后单击“**下一步**”。
    
7. 单击“**发布**”。
    
有关对适合于以 沙盒解决方案 形式发布的表单模板的方案进行演示的示例解决方案，请参阅[示例沙盒解决方案](sample-sandboxed-solutions.md)。
  
### <a name="publishing-form-templates-as-administrator-deployed-solutions"></a>以管理员部署的解决方案的形式发布表单模板

如果您的表单有多个数据连接、需要安全信任安全性或者您需要服务器场范围的模板，则建议以经管理员核准的模板的方式发布表单。
  
服务器场管理员必须先完成几个步骤，然后才能在 SharePoint 上使用管理员部署的解决方案，并且开发人员必须在管理员参与之前准备好该解决方案。
  
首先，如果您的表单将要以完全信任的形式部署，则您必须按以下过程中所述的方式设置安全级别。
  
### <a name="to-set-the-security-level-of-a-form-template-to-full-trust"></a>将表单模板的安全级别设置为完全信任

1. 在 InfoPath 设计器中打开表单模板。
    
2. 单击“**文件**”选项卡，在“**信息**”选项卡上单击“**表单选项**”。
    
3. 单击“**安全和信任**”类别，然后清除“**自动确定安全级别**”复选框。 
    
4. 选择“**完全信任**”。
    
然后，通过使用以下过程发布表单，但要注意与标准发布过程有一些不同之处。
  
### <a name="to-publish-an-administrator-deployed-solution"></a>发布管理员部署的解决方案

1. 在“**发布向导**”的第一页中，指定 SharePoint Server 2010 或 SharePoint Foundation 2010 站点的位置，然后单击“**下一步**”。
    
2. InfoPath 将自动选中向导第二页上的“**经管理员核准的表单模板**”复选框。 单击 **“下一步”**。
    
3. 第三页是管理员部署的解决方案所特有的。请将表单发布到本地存储，而不要选择 SharePoint Server。SharePoint 管理员在管理员部署过程中将从此位置上载文件。
    
4. 完成“**发布向导**”的其余页面。
    

