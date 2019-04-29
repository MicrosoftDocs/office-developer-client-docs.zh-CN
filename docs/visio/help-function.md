---
title: HELP 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251436
localization_priority: Normal
ms.assetid: 5b358c38-6ed1-3fbe-c1d1-1a56ebbaa870
description: 打开 HTML 帮助文件, 其中包含指定的关键字在搜索框中。
ms.openlocfilehash: 639d10bf489d1ad09aef1522d3cbc743bbe66f6f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431335"
---
# <a name="help-function"></a>HELP 函数

打开 HTML 帮助文件, 其中包含指定的*关键字*在**搜索**框中。 
  
## <a name="syntax"></a>语法

HELP ("* * *filename .chm! 关键字** *") 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _文件名 .chm! 关键字_ <br/> |必需  <br/> |**String** <br/> | 要搜索的帮助文件的文件名和关键字。  <br/> |
   
## <a name="remarks"></a>说明

如果未指定*关键字*, 则帮助函数将打开帮助文件的内容页。 
  
## <a name="example"></a>示例

帮助 ("visio .chm! shapesheet") 
  
打开文件 Visio 帮助文件，并显示关键字为“shapesheet”的主题列表。 
  

