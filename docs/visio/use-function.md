---
title: USE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251510
localization_priority: Normal
ms.assetid: 410c4187-21f3-d959-750e-9dc6095fba9a
description: 当放置在 LinePattern、FillPattern、BeginArrow 或 EndArrow 单元格中时, 将线型、填充图案或线端名名称应用于形状。
ms.openlocfilehash: ddd15c1c127fafa1a230545d544c74956f5c0262
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422822"
---
# <a name="use-function"></a>USE 函数

当放置在 LinePattern、FillPattern、BeginArrow 或 EndArrow 单元格中时, 将线型、填充图案或线端名_名称_应用于形状。 
  
## <a name="syntax"></a>语法

USE ("* * *name* * *") 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _name_ <br/> |必需  <br/> |**String** <br/> |是有效主控形状名称的任何字符串。  <br/> |
   
### <a name="return-value"></a>返回值

数字
  
## <a name="remarks"></a>说明

如果文档的文档__ 模具中存在名为的主控形状, 则该图案将应用为线型、填充图案、开始箭头或结束箭头。 
  
此函数始终返回 254。
  
## <a name="example"></a>示例

USE("Railroad Tracks") 
  
通过对包含该公式的形状应用名为 Railroad Tracks 的主控形状图案，设置该形状的格式。 
  

