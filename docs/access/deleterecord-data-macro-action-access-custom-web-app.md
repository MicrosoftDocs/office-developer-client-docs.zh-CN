---
title: 'DeleteRecord Access 自定义 Web (的 DeleteRecord 数据宏) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: f6b68a9a-e04a-476e-a407-b1779fea1953
description: 可以使用 DeleteRecord 操作删除记录。
ms.openlocfilehash: 0e8a658b944e894e4d4014fb3d3d9a583efbee8d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423151"
---
# <a name="deleterecord-data-macro-action-access-custom-web-app"></a>DeleteRecord Access 自定义 Web (的 DeleteRecord 数据宏) 

可以使用 **DeleteRecord** 操作删除记录。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="setting"></a>设置

**DeleteRecord** 操作具有下列参数。 
  
|**参数**|**说明**|
|:-----|:-----|
|**Record Alias** <br/> |一个用于标识要删除的记录的字符串。 如果  *未指定 Alias*  参数，则删除当前记录。  <br/> |
   
## <a name="remarks"></a>备注

您可以使用 **LastCreateRecordIdentity** 本地变量来处理在 **CreateRecord** 数据块中创建的最后一条记录。 例如，使用以下语法引用最近创建的记录： 
  
`[LastCreateRecordIdentity]`


