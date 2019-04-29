---
title: Round 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4af7fbe2-ee34-4a52-b55e-ce3983313b5e
description: 返回一个四舍五入或截断到指定长度或精度的数值。
ms.openlocfilehash: 0afab8c3434aef58c4bb25aee22eefd95732797b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413743"
---
# <a name="round-function-access-custom-web-app"></a>Round 函数 (Access 自定义 web 应用程序)

返回一个四舍五入或截断到指定长度或精度的数值。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **四舍五入**(*Number*, *Precision* , [ *TruncateInsteadOfRound* ]) 
  
**Round**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Number*  <br/> |数值表达式。  <br/> |
| *精密*  <br/> |将*数字*舍入到的精度。  *精度*必须为数值表达式。 如果*精度*为正数, 则将*数字*四舍五入为由 length 指定的小数位数。 当*精度*为负数时,*数字*按长度指定, 在小数点的左侧进行四舍五入。  <br/> |
| *TruncateInsteadOfRound*  <br/> |要执行的操作的类型。 省略或设置为0时, 将四舍五入*数字*。 如果指定非0值, 则将截断*Number* 。 默认值为 0。  <br/> |
   
## <a name="remarks"></a>说明

 **Round**始终返回一个值。 如果 length 为负值且大于小数点前的位数, 则**四舍五入**返回0。 
  

