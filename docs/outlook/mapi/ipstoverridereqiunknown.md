---
title: IPSTOVERRIDEREQ IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPSTOVERRIDEREQ
api_type:
- COM
ms.assetid: 22f497de-4afe-4433-965d-c3b5a66b05da
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7f3f6ae2b9849710bf44d3635fc7bb9a62016f48
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356978"
---
# <a name="ipstoverridereq--iunknown"></a>IPSTOVERRIDEREQ : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
访问个人文件夹文件 (PST) 存储提供程序的资源。
  
|||
|:-----|:-----|
|继承自:  <br/> |IUnknown  <br/> |
|实现者：  <br/> |PST 存储提供程序  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
|接口标识符:  <br/> |IID_IPSTOVERRIDEREQ  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[IPSTOVERRIDEREQ::RegisterTrustedPSTOverrideHandler](ipstoverridereq-registertrustedpstoverridehandler.md) <br/> |启动个人文件夹 (.pst) 文件的解锁过程。  <br/> |
   
## <a name="remarks"></a>注解

PST 替代处理程序接口标识符可能不是在您当前拥有的可下载头文件中定义的, 在这种情况下, 您将在[MAPI 常量](mapi-constants.md)主题中找到它们, 并且可以将它们复制并添加到代码中。 使用 Microsoft Windows 软件开发工具包 (SDK) 头文件 guiddef.h 中定义的 DEFINE_GUID 宏将全局唯一标识符 (GUID) 符号名称与它们的值关联。 
  
有关详细信息, 请参阅[如何实现 PST 替代处理程序以绕过 Outlook 2007 中的 pstdisablegrow 可策略](https://support.microsoft.com/kb/956070)。
  
## <a name="see-also"></a>另请参阅



[IPSTOVERRIDE1 : IUnknown](ipstoverride1iunknown.md)

