---
title: IPSTOVERRIDE1 IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPSTOVERRIDE1
api_type:
- COM
ms.assetid: d26cee81-45ea-4fd3-8a54-5f35264b5d6a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5208e77f3605b5ba861f68786d8fe5e91b990d32
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315496"
---
# <a name="ipstoverride1--iunknown"></a>IPSTOVERRIDE1 : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
允许 PST 存储 (个人) 文件覆盖 PSTDisableGrow 策略。
  
|||
|:-----|:-----|
|继承自：  <br/> |IUnknown  <br/> |
|实现者：  <br/> |PST 存储提供程序  <br/> |
|调用者：  <br/> |客户端  <br/> |
|接口标识符：  <br/> |IID_IPSTOVERRIDE1  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[IPSTOVERRIDE1::GetPersistedRegistrations](ipstoverride1-getpersistedregistrations.md) <br/> |检索个人文件夹的注册列表 (.pst) 文件。  <br/> |
|[IPSTOVERRIDE1::SetPersistedRegistrations](ipstoverride1-setpersistedregistrations.md) <br/> |注册个人文件夹文件以自动解锁，以避免进一步调用 HrTrustedPSTOverrideHandlerCallback。  <br/> |
|[IPSTOVERRIDE1::OverridePSTDisableGrow](ipstoverride1-overridepstdisablegrow.md) <br/> |解锁个人文件夹文件以增长。  <br/> |
   
## <a name="remarks"></a>备注

PST 覆盖处理程序接口标识符可能未在当前具有的可下载头文件中定义，在这种情况下，您将在 [MAPI 常量](mapi-constants.md) 主题中查找它们，并可以复制它们并将其添加到代码中。 使用 Microsoft Windows 软件开发工具包 (SDK) 头文件 guiddef.h 中定义的 DEFINE_GUID 宏将全局唯一标识符 (GUID) 符号名称与它们的值关联。 
  
有关详细信息，请参阅 [如何在 Outlook 2007](https://support.microsoft.com/kb/956070)中实现 PST 覆盖处理程序以绕过 PSTDisableGrow 策略。
  
## <a name="see-also"></a>另请参阅



[IPSTOVERRIDEREQ : IUnknown](ipstoverridereqiunknown.md)

