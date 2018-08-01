---
title: 子字符串函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ae99a0fa-76c4-4c07-9ae9-a7abce23394f
description: 返回文本表达式的一部分。
ms.openlocfilehash: 49d9afefe4b25d91738e518e0ddb2b902067c038
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773621"
---
# <a name="substring-function-access-custom-web-app"></a>子字符串函数 （访问自定义 web 应用程序）

返回文本表达式的一部分。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **子字符串**（*TextExpression*，*启动*，*长度*） 
  
**子字符串**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *TextExpression*  <br/> |文本表达式。  <br/> |
| *Start*  <br/> |指定返回的字符位置开始一个整数表达式。 小于 1 开始时，将会在表达式中指定的第一个字符开始返回的表达式。 在这种情况下，返回的字符数是开始 + 长度 1 的总和或 0 的最大值。 如果 start 大于值表达式中的字符数，则返回零长度表达式。  <br/> |
| *Length*  <br/> |将返回一个正整数表达式，指定表达式的字符数。 如果长度为负数，将生成一个错误和终止语句。 如果 start 和 length 的总和大于表达式中的字符数，则返回整个值表达式从开始的开始。  <br/> |
   

