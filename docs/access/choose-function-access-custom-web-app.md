---
title: 选择函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 70c1ac24-a28f-4401-91d3-61129578bebd
description: 返回的值列表中指定索引处的项。
ms.openlocfilehash: a6db959945bfcfc15993d3979cb9b2b3da0da904
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773443"
---
# <a name="choose-function-access-custom-web-app"></a>选择函数 （访问自定义 web 应用程序）

返回的值列表中指定索引处的项。
  
> [!IMPORTANT]
> [!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

**选择**(*IndexNumber*，*值*，[*Value_n*]) 
  
**选择**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *IndexNumber*  <br/> |一个表示 1 开始的索引到列表中的后面它的各项的整数表达式。  <br/> |
| *值*  <br/> |任何数据类型的值的列表。  <br/> |
   
## <a name="remarks"></a>备注

如果提供的*IndexNumber*不是整数，则值为整数隐式转换。 
  
如果索引值超出值的数组的界限，则**Choose**将返回 NULL。 
  

