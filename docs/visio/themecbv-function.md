---
title: THEMECBV 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ef62f63f-b2ce-4d12-a294-93dbdc9a869d
description: 返回一个 RGB 值或一个整数，它代表文档调色板中的索引，其中作为参数传入的颜色 (数字) 已由活动主题的渐变设置中存储的指定淡色或底纹值进行了修改。
ms.openlocfilehash: 014dc04c5114e296cd2226f3cf04dfb729817578
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429136"
---
# <a name="themecbv-function"></a>THEMECBV 函数

返回一个 RGB 值或一个整数，它代表文档调色板中的索引，其中作为参数传入的颜色 (数字) 已由活动主题的渐变设置中存储的指定淡色或底纹值进行了修改。 
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2013
 
  
## <a name="syntax"></a>语法

 **THEMECBV** ( _color_，  _gradient_stop_number_) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _color_ <br/> |必需  <br/> |**Number** <br/> |一个数字，代表文档的调色板中的索引。  <br/> |
| _gradient_stop_number_ <br/> |必需  <br/> |**Number** <br/> |渐变停止 (淡色) 存储在要应用于颜色的活动主题的渐变设置中。  <br/> |
   
## <a name="return-value"></a>返回值

 **Number**
  
## <a name="remarks"></a>备注

> [!NOTE]
> 如果分配给形状的 QuickStyle 没有渐变，则 THEMECBV 函数对作为参数传入的颜色不执行任何操作。 
  
主题中的渐变设置是一系列编号的渐变停点，对应于"变亮" (淡色) 或"变暗" (阴影) 。 这些底纹和淡色应用于基本颜色以创建渐变颜色效果。
  
**THEMECBV** 函数采用颜色输入，在颜色被指定渐变停点淡色或底纹修改后输出颜色。 如果当前快速样式包含渐变填充，则淡色和底纹来自主题的定义。 如果活动"快速样式"未指定渐变填充或形状设置为"无主题"，则此公式只返回为第一个参数传入的颜色。 
  
## <a name="example"></a>示例

 `THEMECBV(FillForegnd, 5)`
  
返回通过将渐变的第五个渐变停止点中的淡色或底纹应用于 **FillForegnd** 单元格中指定的颜色而创建的颜色。 
  
 `THEMECBV(RGB(255,0,0), 2)`
  
返回通过将第二个渐变停止点应用于红色基色而创建的红色底纹或淡色。
  

