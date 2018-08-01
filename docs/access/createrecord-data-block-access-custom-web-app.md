---
title: CreateRecord 数据块 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 9dd73bae-a8d5-4d8b-b356-01ac72f7e5d9
description: 您可以使用 CreateRecord 数据块在指定表中创建新记录。
ms.openlocfilehash: dc4be7653081c7c02426d84c74b7b56e597706fa
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773479"
---
# <a name="createrecord-data-block-access-custom-web-app"></a>CreateRecord 数据块 （访问自定义 web 应用程序）

您可以使用 **CreateRecord** 数据块在指定表中创建新记录。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
> [!NOTE]
> [!注释] **CreateRecord** 数据块仅适用于数据宏。 
  
## <a name="setting"></a>设置

**DeleteRecord** 数据块具有以下参数。 
  
**DeleteRecord** 数据块具有以下参数。 
  
|**参数名称**|**必需**|**说明**|
|:-----|:-----|:-----|
|**Create a Record In** <br/> |是  <br/> |要在其中创建新记录的表的名称。  <br/> |
|**Alias** <br/> |否  <br/> |一个字符串，标识的记录。 您可以使用记录的别名来标识该记录  <br/> |
   
## <a name="remarks"></a>注释

**CreateRecord** 创建的记录会自动成为当前记录。 
  
**CreateRecord**语句之后，您可以插入提交新记录之前将执行的命令的块。 以下操作适用于 **CreateRecord** 数据块。 
  
||
|:-----|
|[CancelRecordChange 宏操作](cancelrecordchange-macro-action-access-custom-web-app.md) <br/> |
|[Comment 宏语句](comment-macro-block-access-custom-web-app.md) <br/> |
|[Group 宏语句](group-macro-block-access-custom-web-app.md) <br/> |
|[如果...然后...Else 宏语句](ifthenelse-macro-block-access-custom-web-app.md) <br/> |
|[SetField 宏操作](setfield-macro-action-access-custom-web-app.md) <br/> |
|[SetLocalVar 宏操作](setlocalvar-macro-action-access-custom-web-app.md) <br/> |
   
在 **CreateRecord** 操作创建记录后，可使用 **SetField** 操作在该新记录中指定字段值。 
  
如果，则可以使用 **...然后...其他**执行操作的语句基于条件。 
  
若要取消创建记录，可使用 **CancelRecordChange** 操作。此操作将阻止提交更改并退出 **CreateRecord** 数据块。 
  
提交新记录后，可以使用 **LastCreateRecordIdentity** 本地变量来处理该记录。 例如，使用以下语法引用 AssignedTo 字段的最近创建的记录。 
  
`[LastCreateRecordIdentity].[AssignedTo]`


