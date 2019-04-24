---
title: GOTOPAGE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251432
localization_priority: Normal
ms.assetid: b131badf-1656-132e-0aae-eeedb917ba7a
description: 在当前活动窗口中显示名称为 "pagename" 的页面。
ms.openlocfilehash: c96585406b6104aeedbe46c35024a4f13bb0953e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302966"
---
# <a name="gotopage-function"></a>GOTOPAGE 函数

在当前活动窗口中显示名称为 " *pagename* " 的页面。 
  
## <a name="syntax"></a>语法

GOTOPAGE ("* * *pagename* * *") 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _pagename_ <br/> |必需  <br/> |**String** <br/> |要进入的页面的名称。  <br/> |
   
## <a name="remarks"></a>注解

如果一个窗口已经显示了该页，则该窗口就成为活动窗口。 如果*pagename*不存在, 则应用程序将尝试导航到 https:// *pagename* /。 如果 Visio 正用作本地服务器，则 GOTOPAGE 函数将不起作用。 
  
可以使用 HYPERLINK 函数浏览到任何 DOS、UNC 或 URL 路径。 
  
在 Visio 产品的早期版本中，此函数以 _GOTOPAGE 的形式出现。Visio 4.0 版和更高版本接受这两种样式中的任意一种。 
  

