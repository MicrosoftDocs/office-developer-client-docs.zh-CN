---
title: THEMECBV 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ef62f63f-b2ce-4d12-a294-93dbdc9a869d
description: 返回一个 RGB 值或一个整数, 表示文档的调色板中的索引, 其中的颜色 (数字) 以参数形式传入, 并由活动主题的渐变设置中存储的指定淡色或底纹值修改。
ms.openlocfilehash: 014dc04c5114e296cd2226f3cf04dfb729817578
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429136"
---
# <a name="themecbv-function"></a>THEMECBV 函数

返回一个 RGB 值或一个整数, 表示文档的调色板中的索引, 其中的颜色 (数字) 以参数形式传入, 并由活动主题的渐变设置中存储的指定淡色或底纹值修改。 
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2013
 
  
## <a name="syntax"></a>语法

 **THEMECBV**( _color_, _gradient_stop_number_)
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _color_ <br/> |必需  <br/> |**Number** <br/> |表示文档调色板中的索引的数字。  <br/> |
| _gradient_stop_number_ <br/> |必需  <br/> |**Number** <br/> |存储在活动主题的渐变设置中以应用于该颜色的渐变停止点 (淡色或底纹)。  <br/> |
   
## <a name="return-value"></a>返回值

 **Number**
  
## <a name="remarks"></a>说明

> [!NOTE]
> 如果分配给形状的 QuickStyle 没有渐变, 则 THEMECBV 函数对作为参数传入的颜色不执行任何操作。 
  
主题中的渐变设置是一系列与 "变亮" (淡色) 或 "变暗" (底纹) 相对应的编号渐变停止点。 这些底纹和色调应用于基色, 以创建渐变颜色效果。
  
**THEMECBV**函数采用颜色输入, 并在指定的渐变光圈的淡色或底纹修改后输出颜色。 如果当前快速样式包含渐变填充, 则 "淡色" 和 "底纹" 来自主题的定义。 如果活动快速样式未指定渐变填充或形状设置为 "无主题", 则此公式只返回为第一个参数传入的颜色。 
  
## <a name="example"></a>示例

 `THEMECBV(FillForegnd, 5)`
  
返回通过将渐变的第五个渐变停止点中的淡色或底纹应用于**FillForegnd**单元格中指定的颜色而创建的颜色。 
  
 `THEMECBV(RGB(255,0,0), 2)`
  
通过将第二个梯度停止点应用于红色的基色, 返回红色的底纹或淡色。
  

