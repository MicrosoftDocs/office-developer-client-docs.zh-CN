---
title: 关于自定义项类型的冲突解决
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 3f0853fc-f9f2-4314-ac55-47fe1e52d019
description: 本主题介绍如何解决在 Outlook 中创建的自定义项目类型的冲突。
ms.openlocfilehash: 357dd9182f26c4e9e1e264afdee296859e7b3483
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316945"
---
# <a name="about-conflict-resolution-for-custom-item-types"></a>关于自定义项类型的冲突解决

本主题介绍如何解决在 Outlook 中创建的自定义项目类型的冲突。
  
## <a name="conflict-resolution-for-standard-outlook-item-types"></a>标准 Outlook 项目类型的冲突解决

在 Outlook 中, 同一项目的两个或更多副本相互独立修改时, 将发生冲突。 Outlook 在同步过程中检测冲突。 例如, 您可以在 outlook Web App 中更新会议项目, 然后在脱机工作时更新 outlook 中的同一会议项目。 当 Outlook 再次联机并同步客户端计算机和服务器之间的数据时, 它会检测到同一会议项目有两个不同的副本。
  
当 Outlook 同步属于标准 Outlook 项目类型的项目时, 它会考虑特定于该项目类型的属性, 以检测可能的冲突。 Outlook 尝试解决冲突并将生成的副本存储在适当的文件夹中, 而无需请求用户干预。 如果 outlook 认为, 生成的副本可能不包含所有重要数据, outlook 会将冲突副本存储在 "同步问题" 文件夹下的 "冲突" 文件夹中。 
  
> [!NOTE]
> 只有在单击导航窗格中的 "**文件夹列表**" 之后, 才会隐藏同步问题及其子文件夹。 
  
在这种情况下, 用户可以选择转到 "冲突" 文件夹以确认哪些项目发生冲突, 以及是否使用 "冲突" 文件夹中的副本替换 Outlook 决定保留的副本。
  
## <a name="conflict-resolution-for-custom-item-types"></a>自定义项类型的冲突解决方法

### <a name="item-types-and-message-classes"></a>项目类型和邮件类别
  
Outlook 中的所有项目都与一个邮件类别相关联。 例如, 默认情况下, 邮件项目与邮件类 IPM 相关联 **。注释**。 邮件类主要用于标识在 Outlook 中显示项目时应使用的窗体。 outlook 支持映射到 Outlook 中内置项目类型的邮件类别的列表。 若要详细了解邮件类，请参阅[项类型和邮件类](https://msdn.microsoft.com/library/15b709cc-7486-b6c7-88a3-4a4d8e0ab292%28Office.15%29.aspx)。 
  
用户可以创建自定义项目类型, 将自定义邮件类分配给自定义项目类型, 并让 Outlook 使用自定义窗体显示自定义项目类型。 例如, 您可能希望 Outlook 为业务联系人显示自定义商务联系人窗体。 若要执行此操作, 您可以创建自定义邮件类**IPM。请与**此邮件类别联系, 为此邮件类别创建自定义窗体, 并为其分配商务联系人。 
  
### <a name="registering-a-conflict-resolution-scheme-for-custom-item-types"></a>为自定义项类型注册冲突解决方案
  
当您创建自定义邮件类和自定义窗体之外的自定义项目类型时, 您还应考虑 Outlook 如何处理此项目类型的项目的副本之间的冲突。 默认情况下, Outlook 使用所有项目通用的解决方案方案, 不会考虑特定于项目类型的属性, 并且会为用户提供冲突的副本以做出决定。 这是因为自定义项类型可能在自定义窗体中定义自定义字段, 并且可能具有自定义属性和自定义代码。 如果您希望 Outlook 考虑项目特定的属性, 并尝试通过最少的用户干预解决冲突, 则必须通过 Windows 注册表中的设置指定。 可以通过以下两种方式之一实现此目的: 
  
- 通过将组策略设置应用于设置注册表项 ConflictMsgCls 的本地计算机。 下面的示例指定 Outlook 2010 的版本 "14.0": 
  
   `[HKCU]\Software\Policies\Microsoft\Office\14.0\Outlook\Options\ConflictMsgCls`
    
- 通过直接修改用户注册表项 ConflictMsgCls。 下面的示例指定 Outlook 2010 的版本 "14.0": 
  
   `[HKCU]\Software\Microsoft\Office\14.0\Outlook\Options\ConflictMsgCls`
    
通过组策略设置冲突解决优先于直接修改用户注册表项。 注册表项在注册表中的位置取决于 Outlook 的版本。 将自定义邮件类的名称指定为此项下的值。 将值的类型指定为**DWORD**, 将值的数据指定为下表中显示的值之一, 具体取决于所选的分辨率方案。 
  
|Data  | 说明  |
|:-----|:-----|
|0  <br/> |需要用户决策的常见项目解析, 在 Outlook 2002 和早期版本中使用。  <br/> |
|1  <br/> |需要最少用户干预的常见项目分辨率, 这是由于 outlook 2003 中的原因而在 outlook 中使用。  <br/> |
|双面  <br/> |特定于邮件项目的解决方案。  <br/> |
|第三章  <br/> |会议项目特定的解决方案。  <br/> |
|4  <br/> |特定于约会项目的解决方案。  <br/> |
|5  <br/> |特定于联系人项目的分辨率。  <br/> |
|型  <br/> |特定于任务项的解决方案。  <br/> |
|步  <br/> |特定于粘滞便笺项目的分辨率。  <br/> |
|utf-8  <br/> |日记项目特定的解决方案。  <br/> |
   
如果指定了特定于项目的分辨率方案之一 (key data 2 到 8), Outlook 将尝试解决特定于项目的字段 (例如, 约会项目的**开始**和**结束**字段) 中的冲突, 而不会发生用户干预. 如果 outlook 认为解决方案可能导致丢失重要数据, outlook 将在 "冲突" 文件夹中保留相互冲突的副本, 并且用户可以选择转到 "冲突" 文件夹以手动重新解析这些项目, 并覆盖自动办法. 
  
如果要为自定义邮件类 IPM 指定联系人项目特定的解决方案方案, 请使用上面的同一个业务联系人示例 **。请与我们联系**, 可以将其作为**DWORD**值添加到`[HKCU]\Software\Microsoft\Office\15.0\Outlook\Options\ConflictMsgCls`, 并将5指定为数据。 
  
> [!NOTE]
> Outlook 始终使用特定于基于约会邮件类 (IPM) 的自定义邮件类的约会项目的解决方案 **。约会**(例如, **IPM。约会. 个人**)。 
  
## <a name="see-also"></a>另请参阅

- [Outlook 项目对象](https://msdn.microsoft.com/library/6ea4babf-facf-4018-ef5a-4a484e55153a%28Office.15%29.aspx)

