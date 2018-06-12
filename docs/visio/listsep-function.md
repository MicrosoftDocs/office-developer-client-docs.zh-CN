---
title: LISTSEP 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251882
localization_priority: Normal
ms.assetid: 73dc5981-2c8c-e76e-e4bd-e65a7c8db242
description: 返回当前用户区域设置的列表分隔符字符串。
ms.openlocfilehash: 77610b2cf3cc515fb5d3e8b4c6c48de98ab4acc2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780592"
---
# <a name="listsep-function"></a>LISTSEP 函数

返回当前用户区域设置的列表分隔符字符串。
  
## <a name="syntax"></a>语法

LISTSEP ()
  
### <a name="return-value"></a>返回值

String
  
## <a name="example"></a>示例

SETF(GETREF(user.extent)，"最大 （宽度" &amp; ListSep() &amp; "高度"）) 
  

