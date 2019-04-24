---
title: FONT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 20b587ee-87bf-4648-99ec-ddedd703d9fd
description: 返回按名称指定的字体的唯一标识符的整数值。
ms.openlocfilehash: 7ae6fe6dc8bb9c718a358d11d4a6a0227eaf18df
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346135"
---
# <a name="font-function"></a>FONT 函数

返回按名称指定的字体的唯一标识符的整数值。
  
> [!NOTE]
> 在大多数情况下, 字体标识符是特定于系统的。 虽然在文件中使用时仍然建立字体, 但**font**函数提供了跨系统和 Visio 版本的特定字体的一致访问。 建议使用**font**函数来分配字体, 而不是直接引用字体标识符。 
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2013
 
  
## <a name="syntax"></a>语法

 **字体**( _"font_name_string"_)
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _font_name_string_ <br/> |必需  <br/> |**string** <br/> |字体的名称。  <br/> |
   
## <a name="return-value"></a>返回值

整数
  
## <a name="remarks"></a>注解

如果为*font_name_string*提供的字符串与已知字体不匹配, 则此函数将返回一个 #VALUE! 误差. 
  
## <a name="example"></a>示例

 `FONT("Calibri")`
  
返回整数值 (4), 表示 "Calibri" 字体的唯一 ID。
  

