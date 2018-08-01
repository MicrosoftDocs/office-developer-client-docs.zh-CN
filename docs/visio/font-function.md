---
title: FONT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 20b587ee-87bf-4648-99ec-ddedd703d9fd
description: 返回由 name 指定字体的唯一标识符的整数值。
ms.openlocfilehash: 4afd2aa05f2103675bf0df8db5cc7ea21f45fe71
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780296"
---
# <a name="font-function"></a>FONT 函数

返回由 name 指定字体的唯一标识符的整数值。
  
> [!NOTE]
> 在大多数情况下，字体标识符是特定于系统的。 尽管字体保持已一次文件中使用，**字体**函数提供对特定字体具有跨系统和版本的 Visio 一致的访问。 建议使用的**字体**函数分配而不是直接引用字体标识符的字体。 
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2013
 
  
## <a name="syntax"></a>语法

 **字体**( _"font_name_string"_)
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _font_name_string_ <br/> |必需  <br/> |**string** <br/> |字体的名称。  <br/> |
   
## <a name="return-value"></a>返回值

Integer
  
## <a name="remarks"></a>说明

如果为*font_name_string*提供的字符串与已知的字体不匹配，则此函数返回 #VALUE ！ 错误。 
  
## <a name="example"></a>示例

 `FONT("Calibri")`
  
返回表示"宋体"字体的唯一 ID 的整数值 (4)。
  

