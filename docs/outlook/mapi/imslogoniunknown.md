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
ms.openlocfilehash: 991e48aa458a58ad2d7d688e81dbb357ef9bda5b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348711"
---
# <a name="imslogon--iunknown"></a>IMSLogon : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
访问邮件存储区登录对象中的资源。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapispi  <br/> |
|公开者:  <br/> |邮件存储区登录对象  <br/> |
|实现者：  <br/> |邮件存储区提供程序  <br/> |
|调用者：  <br/> |MAPI  <br/> |
|接口标识符:  <br/> |IID_IMSLogon  <br/> |
|指针类型:  <br/> |LPMSLOGON  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[GetLastError](imslogon-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构, 该结构包含有关邮件存储对象的最后一个错误的信息。  <br/> |
|[注销](imslogon-logoff.md) <br/> |注销邮件存储提供程序。  <br/> |
|[OpenEntry](imslogon-openentry.md) <br/> |打开一个文件夹或邮件对象, 并返回指向该对象的指针, 以提供进一步的访问权限。  <br/> |
|[CompareEntryIDs](imslogon-compareentryids.md) <br/> |对两个条目标识符进行比较, 以确定它们是否引用同一个对象。  <br/> |
|[她们](imslogon-advise.md) <br/> |向邮件存储提供程序注册对象, 以获取有关邮件存储区中的更改的通知。  <br/> |
|[Unadvise](imslogon-unadvise.md) <br/> |使用对**IMSLogon:: Advise**方法的调用, 删除以前建立的邮件存储区更改通知的对象注册。  <br/> |
|[OpenStatusEntry](imslogon-openstatusentry.md) <br/> |打开一个 status 对象。  <br/> |
   
## <a name="remarks"></a>注解

邮件存储区登录对象是 MAPI 直接调用的打开邮件存储提供程序的一部分。 MAPI 调用的邮件存储登录对象和客户端应用程序调用的邮件存储对象之间存在一对一的对应关系;您可以将登录和存储对象视为一个公开两个接口的对象。 这两个对象一起创建并一起释放。
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

