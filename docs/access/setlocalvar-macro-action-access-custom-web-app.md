---
title: SetLocalVar 宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 12444313-1cfa-49ff-89da-3030fe75c13e
description: SetLocalVar 操作可创建一个临时变量并将其设置为特定值。
ms.openlocfilehash: 26b1515a8604c02c32135e6e5ccf6fe1e67622f2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19773601"
---
# <a name="setlocalvar-macro-action-access-custom-web-app"></a>SetLocalVar 宏操作 （访问自定义 web 应用程序）

**SetLocalVar** 操作可创建一个临时变量并将其设置为特定值。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
> [!NOTE]
> **SetLocalVar**操作仅适用于数据宏。 
  
## <a name="setting"></a>设置

**SetLocalVar** 操作具有下列参数。 
  
|**参数名称**|**必需**|**说明**|
|:-----|:-----|:-----|
|**名称** <br/> |是  <br/> |一个用于指定变量名称的字符串。  <br/> |
|**Expression** <br/> |可访问  <br/> |一个表达式，用于设置为临时变量的值。 不在表达式前面放等号 （=）。 您可以单击**生成**按钮以使用**表达式生成器**设置此参数。  <br/> |
   

