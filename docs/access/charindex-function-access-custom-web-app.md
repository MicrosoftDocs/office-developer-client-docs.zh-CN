---
title: CharIndex 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 340ed9a8-6f82-4aa8-a951-2c453b3d1ac4
description: 在文本表达式中搜索其他文本表达式, 如果找到, 则返回其起始位置。
ms.openlocfilehash: dc6906f70bc5bb17e12855d69946281909962988
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423130"
---
# <a name="charindex-function-access-custom-web-app"></a>CharIndex 函数 (Access 自定义 web 应用程序)

在文本表达式中搜索其他文本表达式, 如果找到, 则返回其起始位置。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

**CharIndex**(*TextExpression*、 *WithinText*、[*Start*]) 
  
|**参数名称**|**必需**|**描述**|
|:-----|:-----|:-----|
| *TextExpression*  <br/> |是  <br/> |包含要查找的文本的文本表达式。  <br/> |
| *WithinText*  <br/> |是  <br/> |要搜索的文本表达式。  <br/> |
| *Start*  <br/> |否  <br/> |一个整数, 指定*WithinText*中要开始搜索的位置。 如果未指定*Start* , 则为负数, 或者为 0, 则搜索将从*WithinText*的开头开始。  <br/> |
   
## <a name="remarks"></a>说明

如果*TextExpression*或*WithinText*为 null, 则*CharIndex*将返回 NULL。 
  
如果在*WithinText*中找不到*TextExpression* , 则*CharIndex*将返回0。 
  
返回的起始位置是从1开始的, 而不是从0开始的。
  

