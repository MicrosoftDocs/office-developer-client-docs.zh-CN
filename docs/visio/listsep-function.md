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
ms.openlocfilehash: 901442a3c2af8509855b8b038057e7f813634ea1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431405"
---
# <a name="listsep-function"></a>LISTSEP 函数

返回当前用户区域设置的列表分隔符字符串。
  
## <a name="syntax"></a>语法

LISTSEP ()
  
### <a name="return-value"></a>返回值

字符串
  
## <a name="example"></a>示例

SETF (GETREF (user.extent) ， "MAX (Width" &amp; ListSep () &amp; "Height) ")  
  

