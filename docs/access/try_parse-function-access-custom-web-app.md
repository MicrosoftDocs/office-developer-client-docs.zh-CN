---
title: Try_Parse 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ed35263c-b0ad-4269-9caa-c0164015e980
description: 分析到指定的数据类型的区域性中的应用程序的文本值或返回 Null，如果转换无效。
ms.openlocfilehash: 3446e928d9772641f9aea7b956e142f995824b1e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773625"
---
# <a name="tryparse-function-access-custom-web-app"></a>Try_Parse 函数 （访问自定义 web 应用程序）

分析到指定的数据类型的区域性中的应用程序的文本值或返回 Null，如果转换无效。
  
> [!NOTE]
> 本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。* > 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

 **Try_Parse**(*TextExpression*，*数据类型*) 
  
**Try_Parse**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *TextExpression*  <br/> |一个文本表达式，表示要分析到指定的数据类型的格式化的值。  <br/> |
| *DataType*  <br/> |要分析*TextExpression*将数据类型。  <br/> |
   
## <a name="remarks"></a>说明

**Try_Parse**仅用于从字符串转换为日期/时间和号码的类型。 常规类型转换，继续使用**转换**。 
  

