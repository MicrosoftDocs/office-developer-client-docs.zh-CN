---
title: 显示配置属性表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c9386b98-615f-488c-8212-11d9abebbdcf
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fa48e97ed25fe1175ffd3a92ac961dcf5bde50b4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588354"
---
# <a name="displaying-configuration-property-sheets"></a>显示配置属性表

**适用于**： Outlook 2013 |Outlook 2016 
  
传输提供程序使用[IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md)方法实现配置属性表。 调用**DoConfigPropSheet**时, 传输提供程序将一个指针传递到数组属性以及有关如何将其显示的信息。 MAPI 然后会向用户的属性通过标准的对话框中显示。 要实现的用户的一致的界面为带来的好处由于您传输提供程序时使用此属性表机制强烈建议。
  
## <a name="transport-providers"></a>传输提供程序

传输提供程序可以使用[BuildDisplayTable](builddisplaytable.md)函数来简化**DoConfigPropSheet**用于显示表的构造。 传输提供程序也可以直接使用的属性表 API。 若要缓冲区对属性的更改，传输提供程序可以使用[CreateIProp](createiprop.md)函数。 这样可简化处理的取消由用户时用户修改的属性中存储的值。 如果需要，传输提供程序还可以提供一个向导对话框框以简化用户的配置任务。 
  

