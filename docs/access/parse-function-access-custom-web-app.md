---
title: Parse 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 09dee0ae-89b2-449c-a3c8-d6b270710b64
description: 分析文本值, 并使用应用程序的区域性以给定的类型返回其值。
ms.openlocfilehash: d664985ab1d7a7d33b99c52d5bab4aa714767e40
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411132"
---
# <a name="parse-function-access-custom-web-app"></a>Parse 函数 (Access 自定义 web 应用程序)

分析文本值, 并使用应用程序的区域性以给定的类型返回其值。
  
> [!NOTE]
> 本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。* > 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

 **分析**(*TextExpression*, *DataType*) 
  
**Parse**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *TextExpression*  <br/> |表示要分析为指定数据类型的格式化值的文本表达式。  <br/> |
| *DataType*  <br/> |表示为结果请求的数据类型的文本值。  <br/> |
   
## <a name="remarks"></a>说明

仅使用用于将字符串转换为日期/时间和数字类型的**分析**。 对于常规类型转换, 请使用**Convert**函数。 请记住, 在分析字符串值时会发生一定的性能开销。 
  

