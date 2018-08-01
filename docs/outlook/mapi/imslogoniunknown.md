---
title: IMSLogon IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon
api_type:
- COM
ms.assetid: d87093dc-f705-465f-ab3c-944ca0cd3e54
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 42e2633ac6d534be2c75c47b24c1da5ed9771e18
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775925"
---
# <a name="imslogon--iunknown"></a>IMSLogon : IUnknown

  
  
**适用于**： Outlook 
  
在邮件中的访问资源存储登录对象。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapispi.h  <br/> |
|由公开：  <br/> |消息存储登录对象  <br/> |
|通过实现：  <br/> |消息存储提供程序  <br/> |
|调用：  <br/> |MAPI  <br/> |
|接口标识符：  <br/> |IID_IMSLogon  <br/> |
|指针类型：  <br/> |LPMSLOGON  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[时出错](imslogon-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构，其中包含上次消息存储对象发生的错误有关的信息。  <br/> |
|[注销](imslogon-logoff.md) <br/> |注销一条消息存储提供程序。  <br/> |
|[OpenEntry](imslogon-openentry.md) <br/> |打开文件夹或 message 对象并返回指向要进一步提供访问权限的对象的指针。  <br/> |
|[CompareEntryIDs](imslogon-compareentryids.md) <br/> |比较两个条目标识符来确定它们是否引用同一个对象。  <br/> |
|[建议](imslogon-advise.md) <br/> |使用有关邮件存储区中的更改的通知的消息存储提供程序注册的对象。  <br/> |
|[取消通知](imslogon-unadvise.md) <br/> |删除以前使用调用**IMSLogon::Advise**方法建立的邮件存储更改的通知的对象的注册。  <br/> |
|[OpenStatusEntry](imslogon-openstatusentry.md) <br/> |打开状态对象。  <br/> |
   
## <a name="remarks"></a>说明

消息存储登录对象是 MAPI 直接调用打开的邮件存储提供程序的一部分。 MAPI 呼叫和消息存储对象，该客户端应用程序调用; 对象的消息存储登录对象之间没有一对一的对应关系可以当作登录并存储对象作为公开两个接口的一个对象。 两个对象一起创建组合在一起和释放。
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

