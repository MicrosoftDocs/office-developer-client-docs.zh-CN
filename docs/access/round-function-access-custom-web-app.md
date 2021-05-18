---
title: 'Round Function (Access 自定义 Web app) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4af7fbe2-ee34-4a52-b55e-ce3983313b5e
description: 返回一个数值（四舍五入或截断）到指定长度或精度。
ms.openlocfilehash: 0afab8c3434aef58c4bb25aee22eefd95732797b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413743"
---
# <a name="round-function-access-custom-web-app"></a>Round Function (Access 自定义 Web app) 

返回一个数值（四舍五入或截断）到指定长度或精度。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **Round** (*Number*， *Precision*  ， [  *TruncateInsteadOfRound*  ])  
  
**Round** 函数包含下列参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Number*  <br/> |数值表达式。  <br/> |
| *精度*  <br/> |Number  *要舍入*  到的精度。  *Precision*  必须为数值表达式。 当  *Precision*  为正数时  *，Number*  将四舍五入到由 length 指定的小数位数。 当  *Precision*  为负数时  *，Number*  在小数点左侧舍入，如 length 所指定。  <br/> |
| *TruncateInsteadOfRound*  <br/> |要执行的操作的类型。 如果省略或设置为 0，  *则 Number*  将四舍五入。 如果指定值不是 0，则  *Number*  将被截断。 默认值为 0。  <br/> |
   
## <a name="remarks"></a>备注

 **Round** 始终返回一个值。 如果 length 为负数且大于小数点前的位数，则 **Round** 返回 0。 
  

