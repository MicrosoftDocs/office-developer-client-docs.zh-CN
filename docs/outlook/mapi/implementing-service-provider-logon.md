---
title: 实现服务提供程序登录
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3d3c309f-fe60-43a9-beda-16b09ec769db
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 533c00a0c994e7dfc5adc476899553bc39a2a9ab
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401641"
---
# <a name="implementing-service-provider-logon"></a>实现服务提供程序登录

**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 提供程序对象以开始使用您从您的入口点函数返回的指针的登录过程中调用的方法。 该方法，如下所示，取决于您的服务提供程序的类型：
  
- [IABProvider::Logon](iabprovider-logon.md)地址簿提供程序 
    
- [IMSProvider::Logon](imsprovider-logon.md)消息存储提供程序 
    
- [IXPProvider::TransportLogon](ixpprovider-transportlogon.md)传输提供程序 
    
在实现任何登录方法执行以下任务：
  
1. 递增上通过调用其[IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法传递作为输入参数的支持对象的引用计数。 
    
2. 调用支持对象的[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)方法，以访问您的配置文件一节。 
    
3. 调用配置文件部分的[IMAPIProp::SetProps](imapiprop-setprops.md)方法来设置以下属性： 
    
  - **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
    
  - **PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))
    
  - **PR_PROVIDER_DISPLAY**([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))
    
  - **PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))
    
  > [!NOTE]
  > 请务尝试设置配置文件节的**PR_RESOURCE_FLAGS**或**PR_PROVIDER_DLL_NAME**属性。 在登录时，这些属性是只读的。 
  
4. 检查可以存储在配置文件或可从用户所需的配置属性。 有关检查您的配置的详细信息，请参阅[验证服务提供程序配置](verifying-service-provider-configuration.md)。
    
5. 如果您的提供商的地址簿或消息存储提供程序，请调用注册的唯一标识符或[MAPIUID](mapiuid.md)，支持对象的[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)方法。 传输提供程序注册**MAPIUID**结构时 MAPI 调用其[IXPLogon::AddressTypes](ixplogon-addresstypes.md)方法。 有关注册**MAPIUID**的详细信息，请参阅[注册服务提供程序唯一标识符](registering-service-provider-unique-identifiers.md)。
    
6. 实例化一个登录对象并返回具有下列值之一：
    
  - 以指示成功登录的 S_OK。
    
  - MAPI_E_UNCONFIGURED 以指示的一个或多个配置属性不可用。
    
  - MAPI_E_USER_CANCEL 可以指示用户取消配置对话框中，导致无法配置属性。
    
  - MAPI_E_FAILONEPROVIDER 表明，无法配置您的提供商，但 MAPI 应允许其无论使用。 登录方法应返回此值以报告非致命错误，例如提供程序时需要密码和无法提示用户为其因为禁用用户界面。 
    
上述列表中的任务描述服务提供程序 logon 方法的最小实现。 如有必要，可以包含其他功能。 例如，某些提供程序调用[IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md)要更新其登录方法中的状态表。 
  
> [!NOTE]
> 若要获得最佳性能在登录时，避免调用[IMAPISupport::PrepareSubmit](imapisupport-preparesubmit.md)或[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)。 这些呼叫可以完成和控制权归还给您的登录方法之前，必须启动 MAPI 后台处理程序。 
  
## <a name="see-also"></a>另请参阅

- [启动服务提供程序](starting-a-service-provider.md)

