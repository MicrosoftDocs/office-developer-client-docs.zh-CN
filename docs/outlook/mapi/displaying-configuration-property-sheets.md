---
title: 显示配置属性表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c9386b98-615f-488c-8212-11d9abebbdcf
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a796f458e9d30206dc4c6feb37cbdb1e6b6a704b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421310"
---
# <a name="displaying-configuration-property-sheets"></a>显示配置属性表

**适用于**：Outlook 2013 | Outlook 2016 
  
传输提供程序使用[IMAPISupport::D oconfigpropsheet](imapisupport-doconfigpropsheet.md)方法来实现配置属性表。 调用**DoConfigPropSheet**时, 传输提供程序会将指针传递给一组属性, 并提供有关如何显示这些属性的信息。 然后, MAPI 通过标准对话框向用户显示属性。 强烈建议您在实现传输提供程序时使用此属性表机制, 因为对一致接口的用户有益。
  
## <a name="transport-providers"></a>传输提供程序

传输提供程序可以使用[BuildDisplayTable](builddisplaytable.md)函数来简化显示表的构造, 以便与**DoConfigPropSheet**一起使用。 传输提供程序还可以直接使用属性表 API。 若要缓冲对属性的更改, 传输提供程序可以使用[CreateIProp](createiprop.md)函数。 这简化了用户在用户修改存储在属性中的值时处理取消的操作。 如果需要, 传输提供程序还可以提供向导对话框来简化用户的配置任务。 
  

