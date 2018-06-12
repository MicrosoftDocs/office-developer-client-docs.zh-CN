---
title: DateFromParts 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4fa49d5f-12ea-4d14-9a03-28418f01746c
description: 返回指定的年、 月和日的 date 值。
ms.openlocfilehash: 5a2ff76d99076cf9f53b0dce8c5019f38d910f58
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773409"
---
# <a name="datefromparts-function-access-custom-web-app"></a>DateFromParts 函数 （访问自定义 web 应用程序）

返回指定的年、 月和日的 date 值。
  
> [!NOTE]
> 本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。* > 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

**DateFromParts**（*年*、*月*、*日*） 
  
**DateFromParts**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *year()*  <br/> |指定一年的整数表达式。  <br/> |
| *month*  <br/> |整数表达式，指定一个月、 从 1 到 12。  <br/> |
| *日。*  <br/> |指定一天的整数表达式。  <br/> |
   
## <a name="remarks"></a>备注

**DateFromParts**返回设置为指定的年、 月和日和设置为默认值的时间部分的日期部分与一个 date 值。 如果参数不是有效的则引发一个错误。 如果需要参数为 null，则返回 NULL。 
  
## <a name="example"></a>示例

以下表达式使用**DateFromParts**函数计算当前月份的第一天。 
  
`DateFromParts(Year(Today()),Month(Today()),1)`



