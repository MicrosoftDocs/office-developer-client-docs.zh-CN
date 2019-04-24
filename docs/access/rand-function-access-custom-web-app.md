---
title: Rand 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6390b325-025e-4546-bb19-1cd1c45ceb5a
description: 返回介于0和1之间的伪随机数字。
ms.openlocfilehash: 02d914de9d74083a6ebf76f6d0e556fe51954a24
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307992"
---
# <a name="rand-function-access-custom-web-app"></a>Rand 函数 (Access 自定义 web 应用程序)

返回介于0和1之间的伪随机数字。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **Rand**([ *Seed* ]) 
  
**Rand**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Seed*  <br/> |提供种子值的整数表达式。 如果未指定*种子*, 则会随机分配种子值。  <br/> |
   
## <a name="remarks"></a>注解

对具有相同种子的**Rand**函数的重复调用将返回相同的结果。 
  

