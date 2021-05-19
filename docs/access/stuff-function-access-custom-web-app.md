---
title: 'Stuff 函数 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4d8d6a34-f884-40a4-b330-5c104d16cf97
description: 将文本字符串插入到另一个文本字符串中。 它将删除起始位置第一个字符串中指定长度的字符，然后将第二个字符串插入到起始位置的第一个字符串中。
ms.openlocfilehash: 591823952faa0d593b6db1f5bfb00cc68a894a8d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427673"
---
# <a name="stuff-function-access-custom-web-app"></a>Stuff 函数 (Access 自定义 Web 应用) 

将文本字符串插入到另一个文本字符串中。 它将删除起始位置第一个字符串中指定长度的字符，然后将第二个字符串插入到起始位置的第一个字符串中。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **Stuff** (*IntoTextExpression*、 *Start*、 *Length*、 *ThisTextExpression*)  
  
**Stuff** 函数包含下列参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *IntoTextExpression*  <br/> |一个文本表达式，指定将  *插入 ThisTextExpression*  指定的文本的文本。  <br/> |
| *Start*  <br/> |一个整数值，指定开始删除和插入的位置。 如果 start 或 length 为负数，则返回空字符串。 如果 start 长于第一  *个 IntoTextExpression，*  则返回空字符串。  <br/> |
| *Length*  <br/> |指定要删除的字符数的整数。 如果 length 长于  *第一个 IntoTextExpression*  ，则删除将最多发生在最后一  *个 IntoTextExpression 中的最后一个字符*  。  <br/> |
| *ThisTextExpression*  <br/> |文本表达式顶帽指定要插入到  *IntoTextExpression 中的文本*  。 此表达式将替换自 Start 开始的  *IntoTextExpression*  *的长度字符*  。  <br/> |
   
## <a name="remarks"></a>备注

如果  *Start*  或  *Length*  参数为负数，或者起始位置大于第一个字符串的长度，则返回空字符串。 如果起始位置为 0，则返回 null 值。 如果要删除的长度大于第一个字符串的长度，则删除该长度为第一个字符串的第一个字符。 
  

