---
title: 材料 （英文） 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4d8d6a34-f884-40a4-b330-5c104d16cf97
description: 其他文本字符串中插入的文本字符串。 删除指定的开始位置处的第一个字符串中的字符长度及其的开始位置处的第一个字符串中插入第二个字符串。
ms.openlocfilehash: 5540bb5936803370835a0c3d80b420edc13d0de6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773609"
---
# <a name="stuff-function-access-custom-web-app"></a>材料 （英文） 函数 （访问自定义 web 应用程序）

其他文本字符串中插入的文本字符串。 删除指定的开始位置处的第一个字符串中的字符长度及其的开始位置处的第一个字符串中插入第二个字符串。
  
> [!IMPORTANT]
> [!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **材料 （英文)**（*IntoTextExpression*，*启动*，*长度*， *ThisTextExpression*） 
  
**资料**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *IntoTextExpression*  <br/> |指定将插入*ThisTextExpression*指定的文本的文本的文本表达式。  <br/> |
| *Start*  <br/> |一个整数值，指定要启动删除和插入的位置。 如果开始或长度为负数，则返回空字符串。 如果开始长于第一个*IntoTextExpression* ，则返回空字符串。  <br/> |
| *Length*  <br/> |一个整数，指定要删除的字符数。 如果长度大于第一个*IntoTextExpression* ，删除发生最多为最后一个*IntoTextExpression*中的最后一个字符。  <br/> |
| *ThisTextExpression*  <br/> |文本表达式帽指定*IntoTextExpression*中插入的文本。 该表达式将替换开头*开始*的*IntoTextExpression*长度的字符。  <br/> |
   
## <a name="remarks"></a>备注

如果*启动*或*长度*参数为负，或如果的起始位置大于第一个字符串的长度，则返回空字符串。 如果的起始位置为 0，则返回 null 值。 如果要删除的长度超过的第一个字符串，它将删除第一个字符串中的第一个字符。 
  

