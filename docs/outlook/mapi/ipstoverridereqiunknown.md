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
ms.openlocfilehash: 6ee4524d08e334df858c2f035f1b21bd2b0a1c8b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776052"
---
# <a name="ipstoverridereq--iunknown"></a>IPSTOVERRIDEREQ : IUnknown

  
  
**适用于**： Outlook 
  
访问资源的个人文件夹文件 (PST) 存储提供程序。
  
|||
|:-----|:-----|
|继承：  <br/> |IUnknown  <br/> |
|通过实现：  <br/> |PST 存储提供程序  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IPSTOVERRIDEREQ  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[IPSTOVERRIDEREQ::RegisterTrustedPSTOverrideHandler](ipstoverridereq-registertrustedpstoverridehandler.md) <br/> |启动个人文件夹 (.pst) 文件的解除过程。  <br/> |
   
## <a name="remarks"></a>说明

未可能可下载头文件后，这种情况下将在[MAPI 常量](mapi-constants.md)主题中，找到这些和可以复制，并将其添加到您的代码中定义 PST 重写处理程序界面标识符。 使用 Microsoft Windows 软件开发工具包 (SDK) 标头文件 guiddef.h 中定义的 DEFINE_GUID 宏将全局唯一标识符 (GUID) 的符号名称相关联的值。 
  
有关详细信息，请参阅[如何实现 PST 重写处理程序，以绕过 Outlook 2007 中的 PSTDisableGrow 策略](http://support.microsoft.com/kb/956070)。
  
## <a name="see-also"></a>另请参阅



[IPSTOVERRIDE1 : IUnknown](ipstoverride1iunknown.md)

