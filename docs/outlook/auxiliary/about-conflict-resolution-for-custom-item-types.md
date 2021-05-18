---
title: 关于自定义项类型的冲突解决
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 3f0853fc-f9f2-4314-ac55-47fe1e52d019
description: 本主题介绍如何解决在自定义项类型中创建的自定义Outlook。
ms.openlocfilehash: 357dd9182f26c4e9e1e264afdee296859e7b3483
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316945"
---
# <a name="about-conflict-resolution-for-custom-item-types"></a>关于自定义项类型的冲突解决

本主题介绍如何解决在自定义项类型中创建的自定义Outlook。
  
## <a name="conflict-resolution-for-standard-outlook-item-types"></a>标准项目类型的Outlook解决方案

在Outlook中，如果同一项目的两个或多个副本相互独立修改，则会出现冲突。 Outlook同步期间检测冲突。 例如，在脱机工作时，Outlook Web App联机更新会议项目Outlook更新会议项目。 当Outlook再次联机并同步客户端计算机和服务器之间的数据时，它会检测到同一会议项目有两个不同的副本。
  
当Outlook同步属于标准项目Outlook项类型的项目时，它会考虑特定于该项目类型的属性，以检测可能的冲突。 Outlook尝试解决冲突，将结果副本存储在相应的文件夹中，而无需请求用户干预。 如果 Outlook认为结果副本可能不包含所有必需数据，Outlook 将冲突副本存储在"同步问题"文件夹下的"冲突"文件夹中。 
  
> [!NOTE]
> 在导航窗格中单击"文件夹列表"之前，将隐藏"同步问题" **及其子文件夹** 。 
  
在这种情况下，用户可以选择转到"冲突"文件夹，以验证哪些项目存在冲突，以及是否使用"冲突"文件夹中的副本来替换Outlook保留的副本。
  
## <a name="conflict-resolution-for-custom-item-types"></a>自定义项类型的冲突解决

### <a name="item-types-and-message-classes"></a>项目类型和邮件类别
  
邮件Outlook项均与邮件类关联。 例如，默认情况下，邮件项目与邮件类 **IPM 关联。注意**。 邮件类主要用于标识应该用于显示项目在邮件Outlook。 Outlook支持映射到内置到项目类型的邮件类Outlook。 若要详细了解邮件类，请参阅[项类型和邮件类](https://msdn.microsoft.com/library/15b709cc-7486-b6c7-88a3-4a4d8e0ab292%28Office.15%29.aspx)。 
  
用户可以创建自定义项目类型、将自定义邮件类分配给自定义项目类型，Outlook自定义窗体来显示自定义项目类型。 例如，您可能需要Outlook显示业务联系人的自定义业务联系人窗体。 为此，你可以创建自定义邮件类 **IPM。Contact.Business，** 为此邮件类创建自定义窗体，并分配具有此邮件类的业务联系人。 
  
### <a name="registering-a-conflict-resolution-scheme-for-custom-item-types"></a>为自定义项目类型注册冲突解决方案
  
创建自定义项目类型时，除了自定义邮件类和自定义窗体外，还应考虑希望 Outlook 如何处理此项目类型的项目副本之间的冲突。 默认情况下，Outlook所有项目通用的解决方案方案，不考虑特定于项目类型的属性，并且会提供冲突的副本供用户做出决定。 这是因为自定义项类型可能在自定义表单中定义自定义域，并且可能具有自定义属性和自定义代码。 如果您希望Outlook项目特定的属性，并尝试以最少的用户干预解决冲突，则必须通过 Windows 注册表中的设置来指定。 这可以通过两种方式之一实现： 
  
- 将组策略设置应用于设置注册表项 ConflictMsgCls 的本地计算机。 以下示例为 2010 Outlook版本"14.0"： 
  
   `[HKCU]\Software\Policies\Microsoft\Office\14.0\Outlook\Options\ConflictMsgCls`
    
- 通过直接修改用户注册表项 ConflictMsgCls。 以下示例为 2010 Outlook版本"14.0"： 
  
   `[HKCU]\Software\Microsoft\Office\14.0\Outlook\Options\ConflictMsgCls`
    
通过组策略设置冲突解决优先于直接修改用户注册表项。 注册表中项的位置取决于注册表Outlook。 您将自定义邮件类的名称指定为此键下的值。 根据你选择的解析方案，将值的类型指定为 **DWORD**，将值的数据指定为下表中显示的值之一。 
  
|数据  | 说明  |
|:-----|:-----|
|0  <br/> |需要用户决策的常见项目解决方案，如 Outlook 2002 和早期版本中使用的。  <br/> |
|1  <br/> |需要最少的用户干预的常见项目解决方案，Outlook 2003 Outlook中。  <br/> |
|2  <br/> |特定于邮件项目的解决方法。  <br/> |
|3  <br/> |特定于会议项目的解决方法。  <br/> |
|4   <br/> |特定于约会项目的解决方法。  <br/> |
|5   <br/> |特定于联系人项目的解决方法。  <br/> |
|6   <br/> |特定于任务项的解决方法。  <br/> |
|7   <br/> |特定于粘滞便笺项的分辨率。  <br/> |
|8   <br/> |特定于日记项目的解决方法。  <br/> |
   
如果指定项目特定的解决方案方案之一 (键数据 2 到 8) ，Outlook 将尝试解决特定于项目的字段 (例如，约会项目) 的"开始"和"结束"字段在无需用户干预的情况下自动解决冲突。 如果 Outlook认为解决方案可能导致基本数据丢失，Outlook 将在"冲突"文件夹中保留冲突的副本，用户可以选择转到"冲突"文件夹手动重新解决这些项目并覆盖自动解决。 
  
如果要为自定义邮件类 IPM 指定联系人项目特定的解析方案，请使用相同的业务联系人 **示例。Contact.Business**，可以在 下将其添加为 **DWORD** 值  `[HKCU]\Software\Microsoft\Office\15.0\Outlook\Options\ConflictMsgCls` ，并指定 5 作为数据。 
  
> [!NOTE]
> Outlook始终使用特定于基于约会邮件类别 IPM 的自定义邮件类的约会项目的解析 **方案。约会** (例如 **IPM。Appointment.Personal**) 。 
  
## <a name="see-also"></a>另请参阅

- [Outlook 项目对象](https://msdn.microsoft.com/library/6ea4babf-facf-4018-ef5a-4a484e55153a%28Office.15%29.aspx)

