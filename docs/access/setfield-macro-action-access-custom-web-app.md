---
title: 'SetField 宏操作 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 9ae292b0-fde0-4c2b-ba23-23e90365597d
description: SetField 操作可用于向字段分配值。
ms.openlocfilehash: c67c66c238b68512aec90cf6d82d7d497e16ecf1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432924"
---
# <a name="setfield-macro-action-access-custom-web-app"></a>SetField 宏操作 (Access 自定义 Web 应用) 

**SetField** 操作可用于向字段分配值。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
> [!NOTE]
> **SetField** 操作仅适用于数据宏。 
  
## <a name="setting"></a>设置

下表列出了 **SetField** 操作的相关参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
|**名称** <br/> |一个用于标识字段的字符串。  <br/> |
|**值** <br/> |指定要分配给字段的值的表达式。  <br/> |
   
## <a name="remarks"></a>备注

**SetField** 操作不能在 **[CreateRecord](createrecord-data-block-access-custom-web-app.md)** 或 **[EditRecord](editrecord-data-block-access-custom-web-app.md)** 数据块之外使用。 
  

