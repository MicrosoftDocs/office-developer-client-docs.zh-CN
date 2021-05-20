---
title: 'OpenPopup 宏操作 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 850de802-e417-4884-8d14-571de52aa391
description: 在弹出窗口中打开指定的视图。
ms.openlocfilehash: 2a8b67fcbf31c42f13b36f06d14d9d046be68c68
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427386"
---
# <a name="openpopup-macro-action-access-custom-web-app"></a>OpenPopup 宏操作 (Access 自定义 Web 应用) 

在弹出窗口中打开指定的视图。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **OpenPopup** (*View*、 *Where=*、 *Order By*)  
  
**OpenPopup** 操作包含下列参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *View*  <br/> |要打开的视图的名称。  <br/> |
| *Where=*  <br/> |一个有效的 SQL WHERE 子句 (没有单词 WHERE) 来限制视图中的记录。  <br/> |
| *Order By*  <br/> |一个字符串表达式，包含作为记录排序依据的一个或多个字段的名称或可选的 ASC 或 DESC 关键字。 默认情况下，此参数为空。  <br/> |
   
## <a name="remarks"></a>备注

处理 **OpenPopup 操作后，当前** 宏结束。 
  
调用 **OpenPopup** 操作时，将清除用户应用的任何排序或筛选。 
  
*OrderBy* 参数是您希望对记录进行排序的一个或多个字段的名称。 如果使用多个字段名称，需用逗号 (,) 分隔每个名称。 
  
设置  *OrderBy 参数*  时，默认情况下记录按升序排序。 
  

