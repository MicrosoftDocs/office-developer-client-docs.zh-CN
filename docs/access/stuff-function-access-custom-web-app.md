---
title: 内容功能 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4d8d6a34-f884-40a4-b330-5c104d16cf97
description: 将文本字符串插入另一个文本字符串。 它在起始位置删除第一个字符串中的指定长度的字符, 然后将第二个字符串插入到第一个字符串中的起始位置。
ms.openlocfilehash: 591823952faa0d593b6db1f5bfb00cc68a894a8d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427673"
---
# <a name="stuff-function-access-custom-web-app"></a>内容功能 (Access 自定义 web 应用程序)

将文本字符串插入另一个文本字符串。 它在起始位置删除第一个字符串中的指定长度的字符, 然后将第二个字符串插入到第一个字符串中的起始位置。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **内容**(*IntoTextExpression*、 *Start*、 *Length*、 *ThisTextExpression*) 
  
**内容**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *IntoTextExpression*  <br/> |一个文本表达式, 指定将在其中插入*ThisTextExpression*指定的文本的文本。  <br/> |
| *Start*  <br/> |一个整数值, 用于指定要开始删除和插入的位置。 如果 start 或 length 为负值, 则返回一个空字符串。 如果 start 长于第一个*IntoTextExpression* , 则返回 null 字符串。  <br/> |
| *Length*  <br/> |一个整数, 指定要删除的字符数。 如果 length 比第一个*IntoTextExpression*长, 则在最后一个*IntoTextExpression*中的最后一个字符处进行删除。  <br/> |
| *ThisTextExpression*  <br/> |文本表达式 hat 指定要插入到*IntoTextExpression*中的文本。 此表达式将替换*IntoTextExpression*从*Start 开始*的长度字符。  <br/> |
   
## <a name="remarks"></a>说明

如果*Start*或*Length*参数为负, 或者起始位置大于第一个字符串的长度, 则返回 null 字符串。 如果起始位置为 0, 则返回 null 值。 如果要删除的长度超过第一个字符串, 将被删除为第一个字符串中的第一个字符。 
  

