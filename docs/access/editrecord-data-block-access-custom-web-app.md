---
title: EditRecord 数据块 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 54975434-78b2-4010-b2f9-f277831fa92e
description: 您可以使用 EditRecord 数据块更改现有记录中包含的值。
ms.openlocfilehash: 6c214e48326a93cff220b5436d7e7802cd6e3431
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773434"
---
# <a name="editrecord-data-block-access-custom-web-app"></a>EditRecord 数据块 （访问自定义 web 应用程序）

您可以使用 **EditRecord** 数据块更改现有记录中包含的值。 
  
> [!IMPORTANT]
> [!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
> [!NOTE]
> [!注释] **EditRecord** 数据块仅适用于数据宏。 
  
## <a name="setting"></a>设置

**EditRecord** 数据块具有以下参数。 
  
|**参数**|**说明**|
|:-----|:-----|
|**Alias** <br/> |一个字符串，标识要编辑的记录。 如果不指定*Alias*参数，则被编辑当前记录。  <br/> |
   
## <a name="remarks"></a>备注

**EditRecord**语句之后, 可插入的命令将执行提交到记录更改之前的块。 **EditRecord**数据块有以下操作。 
  
||
|:-----|
|[CancelRecordChange 宏操作](cancelrecordchange-macro-action-access-custom-web-app.md) <br/> |
|[注释宏语句](comment-macro-block-access-custom-web-app.md) <br/> |
|[Group 宏语句](group-macro-block-access-custom-web-app.md) <br/> |
|[如果...然后...Else 宏语句](ifthenelse-macro-block-access-custom-web-app.md) <br/> |
|[SetField 宏操作](setfield-macro-action-access-custom-web-app.md) <br/> |
|[SetLocalVar 宏操作](setlocalvar-macro-action-access-custom-web-app.md) <br/> |
   
使用 **SetField** 操作可以指定已编辑记录中某一字段的新值。 
  
如果，则可以使用 **...然后...其他**执行操作的语句基于条件。 
  
若要取消编辑记录，可使用 **CancelRecordChange** 操作。此操作将阻止提交更改并退出 **EditRecord** 数据块。 
  
您可以使用 **LastCreateRecordIdentity** 本地变量来处理在 **CreateRecord** 数据块中创建的最后一条记录。 例如，使用以下语法引用 AssignedTo 字段的最近创建的记录： 
  
`[LastCreateRecordIdentity].[AssignedTo]`


