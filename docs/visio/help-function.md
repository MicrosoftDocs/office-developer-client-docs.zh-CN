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
description: 打开搜索框中的指定关键字的 HTML 帮助文件。
ms.openlocfilehash: 4671b18333bdae953c487662cd880849233df7f5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780391"
---
# <a name="help-function"></a>HELP 函数

打开**搜索**框中的指定*关键字*的 HTML 帮助文件。 
  
## <a name="syntax"></a>语法

帮助 ("* * *filename.chm!keyword* * *") 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _filename.chm!keyword_ <br/> |必需  <br/> |**字符串** <br/> | 要搜索的帮助文件的文件名和关键字。  <br/> |
   
## <a name="remarks"></a>注解

如果未不指定任何*关键字*，则帮助函数将打开的帮助文件的内容页。 
  
## <a name="example"></a>示例

HELP("visio.chm!shapesheet") 
  
打开文件 Visio 帮助文件，并显示关键字为“shapesheet”的主题列表。 
  

