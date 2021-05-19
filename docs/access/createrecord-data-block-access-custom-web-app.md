---
title: 'CreateRecord Data Block (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 9dd73bae-a8d5-4d8b-b356-01ac72f7e5d9
description: 您可以使用 CreateRecord 数据块在指定表中创建新记录。
ms.openlocfilehash: d89b62180dbe50a0c7dab862b70062a47558c25a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421373"
---
# <a name="createrecord-data-block-access-custom-web-app"></a>CreateRecord Data Block (Access 自定义 Web 应用) 

您可以使用 **CreateRecord** 数据块在指定表中创建新记录。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
> [!NOTE]
> **CreateRecord** 数据块仅适用于数据宏。 
  
## <a name="setting"></a>设置

**DeleteRecord** 数据块具有以下参数。 
  
**DeleteRecord** 数据块具有以下参数。 
  
|**参数名称**|**必需**|**描述**|
|:-----|:-----|:-----|
|**Create a Record In** <br/> |是  <br/> |要在其中创建新记录的表的名称。  <br/> |
|**Alias** <br/> |否  <br/> |标识记录的字符串。 您可以使用记录的别名来标识该记录  <br/> |
   
## <a name="remarks"></a>备注

**CreateRecord** 创建的记录会自动成为当前记录。 
  
在 **CreateRecord** 语句之后，可以插入将在提交新记录之前执行的命令块。 以下操作适用于 **CreateRecord** 数据块。 
  
||
|:-----|
|[CancelRecordChange 宏操作](cancelrecordchange-macro-action-access-custom-web-app.md) <br/> |
|[Comment 宏语句](comment-macro-block-access-custom-web-app.md) <br/> |
|[Group 宏语句](group-macro-block-access-custom-web-app.md) <br/> |
|[If...Then...Else 宏语句](ifthenelse-macro-block-access-custom-web-app.md) <br/> |
|[SetField 宏操作](setfield-macro-action-access-custom-web-app.md) <br/> |
|[SetLocalVar 宏操作](setlocalvar-macro-action-access-custom-web-app.md) <br/> |
   
在 **CreateRecord** 操作创建记录后，可使用 **SetField** 操作在该新记录中指定字段值。 
  
可以使用 **If...然后...基于** 条件执行运算的 Else 语句。 
  
若要取消创建记录，可使用 **CancelRecordChange** 操作。此操作将阻止提交更改并退出 **CreateRecord** 数据块。 
  
提交新记录后，可以使用 **LastCreateRecordIdentity** 本地变量来处理该记录。 例如，使用以下语法引用最近创建的记录的 AssignedTo 字段。 
  
`[LastCreateRecordIdentity].[AssignedTo]`


