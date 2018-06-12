---
title: SetField 宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 9ae292b0-fde0-4c2b-ba23-23e90365597d
description: SetField 操作可用于向字段分配值。
ms.openlocfilehash: 1221ea408540a960b948d2d3ece272fd71cb3daf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773607"
---
# <a name="setfield-macro-action-access-custom-web-app"></a>SetField 宏操作 （访问自定义 web 应用程序）

**SetField** 操作可用于向字段分配值。 
  
> [!IMPORTANT]
> [!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
> [!NOTE]
> [!注释] **SetField** 操作仅适用于数据宏。 
  
## <a name="setting"></a>设置

下表列出了 **SetField** 操作的相关参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
|**名称** <br/> |一个用于标识字段的字符串。  <br/> |
|**值** <br/> |一个表达式，指定要分配到的域的值。  <br/> |
   
## <a name="remarks"></a>备注

不能**[CreateRecord](createrecord-data-block-access-custom-web-app.md)** 或**[EditRecord](editrecord-data-block-access-custom-web-app.md)** 数据块外部使用**SetField**操作。 
  

