---
title: TimeFromParts 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7f631b7e-6e3c-46dc-a05f-6a07f9a91268
description: 返回基于指定的部件的时间值。
ms.openlocfilehash: 55a4d1c31fdd2248e3e154d83e803d9f5a5ebb06
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773612"
---
# <a name="timefromparts-function-access-custom-web-app"></a>TimeFromParts 函数 （访问自定义 web 应用程序）

返回基于指定的部件的时间值。
  
> [!NOTE]
> 本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。* > 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

 **TimeFromParts**（*小时*、*分钟*、*秒*） 
  
**TimeFromParts**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *小时*  <br/> |整型表达式，指定小时。  <br/> |
| *分钟*  <br/> |整型表达式，指定分钟。  <br/> |
| *第二个*  <br/> |整型表达式，指定秒。  <br/> |
   
## <a name="see-also"></a>另请参阅

 **TimeFromParts**返回一个完全初始化的时间值。 如果参数均无效，则引发错误。 如果任一参数为 null，则返回 null。 
  

