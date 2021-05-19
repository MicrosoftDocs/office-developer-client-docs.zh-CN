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
  
传输提供程序使用 [IMAPISupport：:D oConfigPropsheet](imapisupport-doconfigpropsheet.md) 方法实现配置属性表。 调用 **DoConfigPropSheet** 时，传输提供程序会传递一个指向属性数组的指针，以及有关如何显示这些属性的信息。 然后，MAPI 通过标准对话框向用户显示属性。 强烈建议在使用传输提供程序属性表此传输提供程序，因为一致的接口对用户的好处。
  
## <a name="transport-providers"></a>传输提供程序

传输提供程序可以使用 [BuildDisplayTable](builddisplaytable.md) 函数来简化用于 **DoConfigPropSheet 的显示表的构造**。 传输提供程序也可以直接属性表 API。 若要缓冲对属性的更改，传输提供程序可以使用 [CreateIProp](createiprop.md) 函数。 这简化了用户在修改属性中存储的值时对取消的处理。 如有必要，传输提供程序还可以提供一个向导对话框来简化用户的配置任务。 
  

