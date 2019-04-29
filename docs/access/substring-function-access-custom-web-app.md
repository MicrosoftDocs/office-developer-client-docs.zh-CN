---
title: SubString 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ae99a0fa-76c4-4c07-9ae9-a7abce23394f
description: 返回文本表达式的一部分。
ms.openlocfilehash: af93620905af366f41bcc50ab6102114acd3db9f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433470"
---
# <a name="substring-function-access-custom-web-app"></a>SubString 函数 (Access 自定义 web 应用程序)

返回文本表达式的一部分。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **子字符串**(*TextExpression*, *Start*, *Length*) 
  
**SubString**函数包含下列参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *TextExpression*  <br/> |文本表达式。  <br/> |
| *Start*  <br/> |integer 表达式, 指定返回的字符的起始位置。 如果 start 小于 1, 则返回的表达式将从 expression 中指定的第一个字符开始。 在这种情况下, 返回的字符数是 start + length-1 或0的总和的最大值。 如果 start 大于值表达式中的字符数, 则返回零长度表达式。  <br/> |
| *Length*  <br/> |一个正整数表达式, 指定将返回的表达式的字符数。 如果 length 为负, 则会生成错误并终止语句。 如果 start 和 length 的总和大于表达式中的字符数, 则返回从 start 开始的整个值表达式。  <br/> |
   

