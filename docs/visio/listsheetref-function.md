---
title: LISTSHEETREF 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 87ddbc35-8577-0a96-20b8-aa7734764c5b
description: 返回对包含形状的列表容器形状的工作表引用。
ms.openlocfilehash: 75c765fab2d287c2da83a659dbbf070d29a9d325
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780619"
---
# <a name="listsheetref-function"></a>LISTSHEETREF 函数

返回对包含形状的列表容器形状的工作表引用。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2010
 
  
## <a name="syntax"></a>语法

LISTMEMBERCOUNT()
  
### <a name="return-value"></a>返回值

ShapeSheet 参考
  
## <a name="remarks"></a>注解

如果形状不是列表成员，则 LISTSHEETREF 函数返回 #REF!。
  
## <a name="example"></a>示例

LISTSHEETREF(1)!Height 
  
返回包含形状的列表容器形状的 Height 单元格中的值。 
  

