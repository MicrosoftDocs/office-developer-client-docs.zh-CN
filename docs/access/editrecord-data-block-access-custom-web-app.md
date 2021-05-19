---
title: 'EditRecord Data Block (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 54975434-78b2-4010-b2f9-f277831fa92e
description: 您可以使用 EditRecord 数据块更改现有记录中包含的值。
ms.openlocfilehash: 0d9ef6c7689b44a0304309a7537e744eff97c809
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418342"
---
# <a name="editrecord-data-block-access-custom-web-app"></a>EditRecord Data Block (Access 自定义 Web 应用) 

您可以使用 **EditRecord** 数据块更改现有记录中包含的值。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
> [!NOTE]
> **EditRecord** 数据块仅适用于数据宏。 
  
## <a name="setting"></a>设置

**EditRecord** 数据块具有以下参数。 
  
|**参数**|**说明**|
|:-----|:-----|
|**Alias** <br/> |一个用于标识要编辑的记录的字符串。 如果  *未指定 Alias*  参数，则编辑当前记录。  <br/> |
   
## <a name="remarks"></a>备注

在 **EditRecord** 语句之后，可以插入将在提交对记录所做的更改之前执行的命令块。 EditRecord 数据块中 **提供了以下** 操作。 
  
||
|:-----|
|[CancelRecordChange 宏操作](cancelrecordchange-macro-action-access-custom-web-app.md) <br/> |
|[Comment 宏语句](comment-macro-block-access-custom-web-app.md) <br/> |
|[Group 宏语句](group-macro-block-access-custom-web-app.md) <br/> |
|[If...Then...Else 宏语句](ifthenelse-macro-block-access-custom-web-app.md) <br/> |
|[SetField 宏操作](setfield-macro-action-access-custom-web-app.md) <br/> |
|[SetLocalVar 宏操作](setlocalvar-macro-action-access-custom-web-app.md) <br/> |
   
使用 **SetField** 操作可以指定已编辑记录中某一字段的新值。 
  
可以使用 **If...然后...基于** 条件执行运算的 Else 语句。 
  
若要取消编辑记录，可使用 **CancelRecordChange** 操作。此操作将阻止提交更改并退出 **EditRecord** 数据块。 
  
您可以使用 **LastCreateRecordIdentity** 本地变量来处理在 **CreateRecord** 数据块中创建的最后一条记录。 例如，使用以下语法引用最近创建的记录的 AssignedTo 字段： 
  
`[LastCreateRecordIdentity].[AssignedTo]`


