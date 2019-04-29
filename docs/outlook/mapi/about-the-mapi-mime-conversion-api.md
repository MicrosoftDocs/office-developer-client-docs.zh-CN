---
title: 关于 MAPI-MIME 转换 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: ffdfdff8-985d-35de-73b1-c34e1932cb9f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7123b2deaa9ae0f26002b486df229ad589009f53
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420435"
---
# <a name="about-the-mapi-mime-conversion-api"></a>关于 MAPI-MIME 转换 API

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI-MIME 转换 API 允许邮件提供程序在 MIME 对象和 MAPI 邮件之间进行转换。 它提供了常量定义、类标识符和接口标识符, 如[MAPI 常量](mapi-constants.md)中所示。 邮件提供程序必须通过调用**CoCreateInstance**函数来 cocreate **[IConverterSession](iconvertersessioniunknown.md)** 的实例。 
  

