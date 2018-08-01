---
title: OpenPopup 宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 850de802-e417-4884-8d14-571de52aa391
description: 在弹出窗口中打开指定的视图。
ms.openlocfilehash: 01e0086dc0b54837cf5f095ec6ac5701b5b0b219
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773575"
---
# <a name="openpopup-macro-action-access-custom-web-app"></a>OpenPopup 宏操作 （访问自定义 web 应用程序）

在弹出窗口中打开指定的视图。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **OpenPopup**(在*视图*中，*其中 =*，*按顺序*) 
  
**OpenPopup**操作包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *View*  <br/> |要打开的视图的名称。  <br/> |
| *其中 =*  <br/> |关键字的有效 SQL WHERE 子句 (不带有单词其中)，它将在视图中的记录。  <br/> |
| *Order By*  <br/> |一个字符串表达式，包含作为记录排序依据的一个或多个字段的名称或可选的 ASC 或 DESC 关键字。 默认情况下，此参数为空。  <br/> |
   
## <a name="remarks"></a>说明

当前的宏结束后处理**OpenPopup**操作。 
  
调用**OpenPopup**操作时，会清除任何排序或筛选用户应用的。 
  
*OrderBy*参数是在您要对记录进行排序的字段的名称。 如果使用多个字段名称，需用逗号 (,) 分隔每个名称。 
  
当设置*OrderBy*参数时，记录将默认情况下按升序排序。 
  

