---
title: CharIndex 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 340ed9a8-6f82-4aa8-a951-2c453b3d1ac4
description: 搜索其他文本表达式，如果其起始位置的返回的文本表达式找到。
ms.openlocfilehash: 86a46f57c64028530217326127eece887127c4c3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773460"
---
# <a name="charindex-function-access-custom-web-app"></a>CharIndex 函数 （访问自定义 web 应用程序）

搜索其他文本表达式，如果其起始位置的返回的文本表达式找到。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

**CharIndex**(*TextExpression*， *WithinText*，[*启动*]) 
  
|**参数名称**|**必需**|**说明**|
|:-----|:-----|:-----|
| *TextExpression*  <br/> |可访问  <br/> |一个包含要找的文本的文本表达式。  <br/> |
| *WithinText*  <br/> |可访问  <br/> |要搜索的文本表达式。  <br/> |
| *Start*  <br/> |否  <br/> |一个整数，指定*WithinText*开始搜索中的位置。 如果*启动*未指定，为负数，或者为 0，则搜索开始*WithinText*开头。  <br/> |
   
## <a name="remarks"></a>说明

如果*TextExpression*或*WithinText*为 NULL，则*CharIndex*将返回 NULL。 
  
如果*WithinText*中找不到*TextExpression* ， *CharIndex*将返回 0。 
  
基于 1，不是从 0 开始，返回的起始位置。
  

