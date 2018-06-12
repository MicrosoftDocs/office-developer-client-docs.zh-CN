---
title: DeleteRecord 数据宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: f6b68a9a-e04a-476e-a407-b1779fea1953
description: 您可以使用 DeleteRecord 操作删除记录。
ms.openlocfilehash: 64742d73ec57b94474c8e27822fd3946c7673336
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773404"
---
# <a name="deleterecord-data-macro-action-access-custom-web-app"></a>DeleteRecord 数据宏操作 （访问自定义 web 应用程序）

可以使用 **DeleteRecord** 操作删除记录。 
  
> [!IMPORTANT]
> [!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="setting"></a>设置

**DeleteRecord**操作具有下列参数。 
  
|**参数**|**说明**|
|:-----|:-----|
|**记录别名** <br/> |一个字符串，标识要删除的记录。 如果未指定*别名*参数，将删除当前记录。  <br/> |
   
## <a name="remarks"></a>注释

您可以使用 **LastCreateRecordIdentity** 本地变量来处理在 **CreateRecord** 数据块中创建的最后一条记录。 例如，使用以下语法引用最近创建的记录： 
  
`[LastCreateRecordIdentity]`


