---
title: 'Parse Function (Access 自定义 Web app) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 09dee0ae-89b2-449c-a3c8-d6b270710b64
description: 使用应用程序的区域性分析文本值，并返回给定类型中的值。
ms.openlocfilehash: d664985ab1d7a7d33b99c52d5bab4aa714767e40
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411132"
---
# <a name="parse-function-access-custom-web-app"></a>Parse Function (Access 自定义 Web app) 

使用应用程序的区域性分析文本值，并返回给定类型中的值。
  
> [!NOTE]
> 本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。* > 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

 **Parse** (*TextExpression*， *DataType*)  
  
**Parse** 函数包含下列参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *TextExpression*  <br/> |一个文本表达式，代表要解析为指定值的格式数据类型。  <br/> |
| *DataType*  <br/> |文本值，数据类型结果请求的值。  <br/> |
   
## <a name="remarks"></a>备注

仅对从字符串转换为日期/时间和数字类型使用 **Parse。** 对于常规类型转换，请使用 **Convert** 函数。 请记住，分析字符串值时存在一定的性能开销。 
  

