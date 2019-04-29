---
title: CALLOUTTARGETREF 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c67cfd32-5911-d8e9-dd51-fd4885dd2b0d
description: 返回对标注形状的目标形状的工作表引用。
ms.openlocfilehash: aeeb919fb2efc175d8e5ce23f464503c13331249
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423011"
---
# <a name="callouttargetref-function"></a>CALLOUTTARGETREF 函数

返回对标注形状的目标形状的工作表引用。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2010
 
  
## <a name="syntax"></a>语法

CALLOUTTARGETREF ()!
  
### <a name="return-value"></a>返回值

ShapeSheet 参考
  
## <a name="remarks"></a>说明

如果形状不是标注形状, 或者形状不与目标形状相关联, 则 CALLOUTTARGETREF 返回 #REF。
  
## <a name="example"></a>示例

CALLOUTTARGETREF ()!高度 
  
返回与标注相关的形状的 Height 单元格中的值。 
  

