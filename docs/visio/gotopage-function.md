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
description: 将显示在当前的活动窗口中具有名称 pagename 页。
ms.openlocfilehash: c96585406b6104aeedbe46c35024a4f13bb0953e
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397147"
---
# <a name="gotopage-function"></a>GOTOPAGE 函数

将显示在当前的活动窗口中具有名称*pagename*页。 
  
## <a name="syntax"></a>语法

GOTOPAGE ("* * *pagename* * *") 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _pagename_ <br/> |必需  <br/> |**字符串** <br/> |要进入的页面的名称。  <br/> |
   
## <a name="remarks"></a>注解

窗口已显示页上，如果该窗口将变为活动状态。 如果不存在*pagename* ，应用程序尝试导航到 https:// *pagename* /。 如果 Visio 正在就地服务器，GOTOPAGE 函数不起作用。 
  
可以使用 HYPERLINK 函数浏览到任何 DOS、UNC 或 URL 路径。 
  
在 Visio 产品的早期版本中，此函数以 _GOTOPAGE 的形式出现。Visio 4.0 版和更高版本接受这两种样式中的任意一种。 
  

