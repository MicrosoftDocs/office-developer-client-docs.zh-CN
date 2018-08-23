---
title: 使用线程安全对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e688db5e-d1a1-4afc-998f-b3d31eb6239b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 49a94b785a51b4b0c3082832145250eec0745a19
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580976"
---
# <a name="using-thread-safe-objects"></a>使用线程安全对象

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
客户端应用程序可以假设对象直接使用或作为回调将始终线程安全除在出现以下情况：
  
- 传输提供程序的状态对象获取通过客户端调用[IMAPISession::OpenEntry](imapisession-openentry.md)条目标识符从提供程序的状态表格行。 
    
- 通过客户端调用[MAPIOpenFormMgr](mapiopenformmgr.md)获取所有 MAPI 表单对象。 表单对象遵循单元模型规则和客户端必须使用它们和仅在用于创建它们的线程上通过它们包含的所有对象。
    
当客户端访问包含关联的状态对象的项标识符状态表中的传输提供程序的行时，客户端可以使用该条目标识符打开状态对象调用**OpenEntry** 。 此状态对象不是线程安全，因为传输提供程序的 MAPI 后台处理程序上下文中运行，并且不维护其状态对象的单独的上下文。 状态对象服从单元模型规则和客户端必须仅在创建它的线程上使用它。 
  
客户端必须还调用[MAPIInitialize](mapiinitialize.md)每个线程上使用完成时使用的任何 MAPI 对象和[MAPIUninitialize](mapiuninitialize.md)之前。 即使要使用对象传递到线程从外部源应将这些呼叫。 **MAPIInitialize**和**MAPIUninitialize**可以从任何地方除从中调用 Win32 **DllMain**函数，由系统时进程和线程初始化并终止，或者调用**时调用的函数LoadLibrary**和**句**函数。 
  
从不应假定间接使用对象可线程安全。 需要作为输入参数的目标接口指针方法返回间接使用对象。 这种方法的示例是**IMAPIProp::CopyTo**和**CopyProps**、 **IMAPIFolder::CopyFolder**和**CopyMessage**和**IMsgServiceAdmin::CopyMsgService**。 如果服务提供商想要在其上以外传递给它的线程从呼叫这样的对象，提供程序负责明确封送处理对象。
  

