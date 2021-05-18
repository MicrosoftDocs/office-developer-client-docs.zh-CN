---
title: 'Choose function (Access custom web app) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 70c1ac24-a28f-4401-91d3-61129578bebd
description: 从值列表返回指定索引中的项。
ms.openlocfilehash: e44655b9c2f4055f1f3dc57befa8adc6884c43b6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414114"
---
# <a name="choose-function-access-custom-web-app"></a>Choose function (Access custom web app) 

从值列表返回指定索引中的项。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

**Choose** (*IndexNumber*， *Value*， [*Value_n*])  
  
**Choose** 函数包含下列参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *IndexNumber*  <br/> |一个整数表达式，表示从 1 到以下项目列表中的索引。  <br/> |
| *值*  <br/> |任何值的列表数据类型。  <br/> |
   
## <a name="remarks"></a>备注

如果提供的  *IndexNumber*  不是整数，则值将隐式转换为整数。 
  
如果索引值超出值数组的界限， **则 Choose** 将返回 NULL。 
  

