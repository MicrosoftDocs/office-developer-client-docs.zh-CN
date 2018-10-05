---
title: 关于自定义项目类型的冲突解决
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 3f0853fc-f9f2-4314-ac55-47fe1e52d019
description: 本主题介绍如何解决 Outlook 中创建的自定义项类型的冲突。
ms.openlocfilehash: 357dd9182f26c4e9e1e264afdee296859e7b3483
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25382986"
---
# <a name="about-conflict-resolution-for-custom-item-types"></a>关于自定义项目类型的冲突解决

本主题介绍如何解决 Outlook 中创建的自定义项类型的冲突。
  
## <a name="conflict-resolution-for-standard-outlook-item-types"></a>指定在冲突解决标准的 Outlook 项目类型

在 Outlook 中，在两个时，会发生冲突或独立于每个其他已修改的同一个项目的多个副本。 Outlook 同步过程中检测冲突。 例如，您可能会更新 online 中 Outlook Web App 的会议项目，然后更新 Outlook 中的同一会议项目，脱机工作时。 当 Outlook 联机再次和客户端计算机和服务器之间同步数据时，它会检测存在相同的会议项目的两个不同的副本。
  
当 Outlook 同步属于标准的 Outlook 项目类型的项目时，它考虑将特定于该项目类型来检测可能出现的冲突的属性。 Outlook 尝试解决冲突，并将结果副本的相应文件夹中存储而不需要用户干预。 在其中 Outlook 会认为，则将结果副本可能不包含所有的基本数据可能的情况下，Outlook 将存储中冲突文件夹的同步问题文件夹下的冲突副本。 
  
> [!NOTE]
> 同步问题及其子文件夹处于隐藏状态的只有单击导航窗格中的**文件夹列表**。 
  
在这种情况下，用户可以选择转到冲突文件夹，以验证哪些项目已存在冲突，以及是否为冲突文件夹中使用的副本，以替换 Outlook 决定要保留的副本。
  
## <a name="conflict-resolution-for-custom-item-types"></a>指定在冲突解决自定义项类型

### <a name="item-types-and-message-classes"></a>项目类型和邮件类
  
在 Outlook 中的所有项都都与邮件类关联。 例如，默认情况下，邮件项目相关联的邮件类**IPM。注意**。 邮件类主要用于标识用于在 Outlook 中显示项目的窗体。 Outlook 支持的邮件类的映射到 Outlook 中内置的项目类型的列表。 若要详细了解邮件类，请参阅[项类型和邮件类](https://msdn.microsoft.com/library/15b709cc-7486-b6c7-88a3-4a4d8e0ab292%28Office.15%29.aspx)。 
  
用户可以创建自定义项类型、 自定义邮件类别分配的自定义项类型，并具有 Outlook 使用自定义窗体显示的自定义项类型。 例如，您可能希望 Outlook 显示自定义业务联系人窗体业务的联系人。 为此，您可以创建自定义邮件类**IPM。Contact.Business**、 创建的此邮件类的自定义窗体并分配与此邮件类的业务联系人。 
  
### <a name="registering-a-conflict-resolution-scheme-for-custom-item-types"></a>注册自定义项类型的冲突解决方案
  
在创建自定义项类型，而不是自定义邮件类和自定义窗体，还应考虑如何您希望 Outlook 处理此项目类型的项目的副本之间的冲突。 默认情况下，Outlook 使用通用于所有项目的解决方案方案、 不考虑属性特定于项类型，并呈现用户做出选择冲突副本。 这是因为自定义项类型可能定义自定义字段中自定义窗体，并且可能包含自定义属性和自定义代码。 如果您希望 Outlook 项特定于属性，请考虑并尝试解决与最少的用户干预的冲突，则必须通过 Windows 注册表中设置指定的。 这可以通过两种方式之一来实现： 
  
- 通过将组策略设置应用到本地计算机的设置的注册表项 ConflictMsgCls。 下面的示例指定 Outlook 2010 中的版本"14.0": 
  
   `[HKCU]\Software\Policies\Microsoft\Office\14.0\Outlook\Options\ConflictMsgCls`
    
- 通过直接修改用户注册表项 ConflictMsgCls。 下面的示例指定 Outlook 2010 中的版本"14.0": 
  
   `[HKCU]\Software\Microsoft\Office\14.0\Outlook\Options\ConflictMsgCls`
    
设置通过组策略指定在冲突解决优先于直接修改用户注册表项。 注册表中的项的位置取决于 Outlook 版本。 为此项下值指定的自定义邮件类别的名称。 指定值的类型为**DWORD**和值的数据为下表，具体取决于您选择的分辨率方案中所示的值之一。 
  
|Data  | 说明  |
|:-----|:-----|
|0  <br/> |需要用户决定，后者用于 Outlook 2002 和早期版本中的常见项分辨率。  <br/> |
|1  <br/> |在 Outlook 中使用 Outlook 2003 以来需要极少用户干预的常用项分辨率。  <br/> |
|2  <br/> |特定于邮件项目的解决方案。  <br/> |
|3  <br/> |向会议项目特定的分辨率。  <br/> |
|4  <br/> |特定于约会项的分辨率。  <br/> |
|5  <br/> |解决方案特定联系人项目。  <br/> |
|6  <br/> |特定于任务项目的解决方案。  <br/> |
|7  <br/> |特定于粘滞便笺项的分辨率。  <br/> |
|8  <br/> |特定于日记项目的解决方案。  <br/> |
   
如果您指定的特定于项目的解决方案方案 （关键数据为 2 到 8） 之一，Outlook 将尝试解决冲突中自动无需用户干预的特定于项的字段 （例如， **Start**和**End**字段的约会项目）. 如果 Outlook 会认为分辨率可能会导致重要数据丢失，Outlook 将保留冲突文件夹中的冲突副本，并且用户可以选择转到冲突文件夹，手动将这些项目重新解析和重写自动解决方法。 
  
如果您想要指定自定义邮件类**IPM 的联系人项特定于解决方案方案，请使用上面的相同业务联系人示例。Contact.Business**，您可以将其添加为下一个**DWORD**值`[HKCU]\Software\Microsoft\Office\15.0\Outlook\Options\ConflictMsgCls`，并指定 5 为数据。 
  
> [!NOTE]
> Outlook 始终使用特定于基于约会邮件类**IPM 的自定义邮件类的约会项目的解决方案方案。约会**（例如， **IPM。Appointment.Personal**)。 
  
## <a name="see-also"></a>另请参阅

- [Outlook 项目对象](https://msdn.microsoft.com/library/6ea4babf-facf-4018-ef5a-4a484e55153a%28Office.15%29.aspx)

