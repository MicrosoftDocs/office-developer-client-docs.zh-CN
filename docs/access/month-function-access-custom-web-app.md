---
title: Month 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5df43594-a434-4fb7-8109-e5cf0401ae09
description: 返回一个 integer 值，该值代表指定日期的月。
ms.openlocfilehash: 5e4a583a5a299456e57b90d7cef41a32b0a6ffba
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773582"
---
# <a name="month-function-access-custom-web-app"></a>Month 函数 （访问自定义 web 应用程序）

返回一个 integer 值，该值代表指定日期的月。
  
> [!NOTE]
> 本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。* > 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

 **月**(*日期*) 
  
**Month**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Date*  <br/> |一个可解析为日期/时间值的表达式。  <br/> |
   
## <a name="remarks"></a>说明

 **月**返回**DatePart** （月、 日期） 相同的值。 
  
如果*日期*包含时间部分，返回值为 1，基本的月份。 
  

