---
title: Round 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4af7fbe2-ee34-4a52-b55e-ce3983313b5e
description: 返回一个数字值，舍入或截断为指定的长度或精度。
ms.openlocfilehash: 5a3df4a4ddd7aace5edf886db5988704e5dd6af3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773604"
---
# <a name="round-function-access-custom-web-app"></a>Round 函数 （访问自定义 web 应用程序）

返回一个数字值，舍入或截断为指定的长度或精度。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **圆**（*号码*、*精度*[ *TruncateInsteadOfRound* ]） 
  
**Round**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Number*  <br/> |数值表达式。  <br/> |
| *精度*  <br/> |精度*数*是要舍入。  *精度*必须是数值表达式。 当*精度*为正数时，则会将*Number*舍入到指定长度的位数。 *精度*时为负数，则会将*Number*舍入指定长度的小数点左侧。  <br/> |
| *TruncateInsteadOfRound*  <br/> |要执行的操作类型。 当省略或设置为 0， *Number*舍入。 指定一个其他大于 0 的值时，*数字*将被截断。 默认值为 0。  <br/> |
   
## <a name="remarks"></a>说明

 **Round**始终返回一个值。 如果长度为负数和大于之前小数点的位数， **Round**返回 0。 
  

