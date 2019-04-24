---
title: 实现服务提供程序登录
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3d3c309f-fe60-43a9-beda-16b09ec769db
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 533c00a0c994e7dfc5adc476899553bc39a2a9ab
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310085"
---
# <a name="implementing-service-provider-logon"></a>实现服务提供程序登录

**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 使用从入口点函数返回的指针调用提供程序对象中的方法, 以开始登录过程。 根据您的服务提供程序的类型, 此方法的不同之处如下:
  
- [IABProvider::](iabprovider-logon.md)通讯簿提供程序的登录名 
    
- [IMSProvider::](imsprovider-logon.md)针对邮件存储提供程序的登录 
    
- [IXPProvider:: TransportLogon](ixpprovider-transportlogon.md)的传输提供程序 
    
在您实施的任何登录方法中执行以下任务:
  
1. 通过调用其[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法来递增作为输入参数传递的 support 对象的引用计数。 
    
2. 调用支持对象的[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)方法以访问您的配置文件部分。 
    
3. 调用配置文件节的[IMAPIProp:: SetProps](imapiprop-setprops.md)方法以设置以下属性: 
    
  - **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
    
  - **PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))
    
  - **PR_PROVIDER_DISPLAY**([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))
    
  - **PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))
    
  > [!NOTE]
  > 请勿尝试设置 profile 节的**PR_RESOURCE_FLAGS**或**PR_PROVIDER_DLL_NAME**属性。 在登录时, 这些属性是只读的。 
  
4. 检查配置所需的属性是否已存储在配置文件中, 或是否可从用户获取。 有关检查配置的详细信息, 请参阅[验证服务提供程序配置](verifying-service-provider-configuration.md)。
    
5. 如果您的提供商是通讯簿或邮件存储提供程序, 则调用支持对象的[IMAPISupport:: SetProviderUID](imapisupport-setprovideruid.md)方法以注册唯一标识符或[MAPIUID](mapiuid.md)。 当 MAPI 调用其[IXPLogon:: AddressTypes](ixplogon-addresstypes.md)方法时, 传输提供程序注册**MAPIUID**结构。 有关注册**MAPIUID**的详细信息, 请参阅[注册服务提供程序唯一标识符](registering-service-provider-unique-identifiers.md)。
    
6. 实例化登录对象, 并返回以下值之一:
    
  - S_OK 表示登录成功。
    
  - MAPI_E_UNCONFIGURED, 以指示一个或多个配置属性不可用。
    
  - MAPI_E_USER_CANCEL 指示用户取消了 "配置" 对话框, 从而导致配置属性不可用。
    
  - MAPI_E_FAILONEPROVIDER 指示无法配置您的提供程序, 但 MAPI 应允许使用它, 而不考虑。 登录方法应返回此值以报告非严重错误, 例如, 当提供程序需要密码时, 如果用户界面被禁用, 则不能提示用户。 
    
前面的任务列表介绍了服务提供程序登录方法的最低实现。 如有必要, 可以包括其他功能。 例如, 某些提供程序调用[IMAPISupport:: ModifyStatusRow](imapisupport-modifystatusrow.md)以在其登录方法中更新状态表。 
  
> [!NOTE]
> 若要在登录时获得最佳性能, 请避免调用[IMAPISupport reparesubmit](imapisupport-preparesubmit.md)或[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md)。 必须先启动 MAPI 后台处理程序, 然后才能完成这些呼叫并将控制返回给您的登录方法。 
  
## <a name="see-also"></a>另请参阅

- [启动服务提供程序](starting-a-service-provider.md)

