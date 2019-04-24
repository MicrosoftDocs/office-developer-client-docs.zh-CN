---
title: PidTagExchangeProfileSectionId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagExchangeProfileSectionId
api_type:
- HeaderDef
ms.assetid: 4ad2f417-be8f-4fc8-9321-82097289074b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ce823159047410a8cea13b7eff5566cd8abaa5b9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316427"
---
# <a name="pidtagexchangeprofilesectionid-canonical-property"></a>PidTagExchangeProfileSectionId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含在使用多个 Microsoft Exchange Server 帐户时用于确定帐户的动态生成的 GUID。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_EMSMDB_SECTION_UID  <br/> |
|标识符:  <br/> |0x3d150102  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |多个 Exchange 帐户  <br/> |
   
## <a name="remarks"></a>注解

microsoft outlook 2010 和 microsoft outlook 2013 支持多个 exchange 帐户, 而不是一个 exchange 帐户。 为了适应多个 Exchange 帐户, MAPI 配置文件的布局已更改。 在 Microsoft Office Outlook 2007 及更低版本中, 配置文件包含专用于 Exchange 设置的固定配置文件部分, 如服务器名称、用户名和脱机文件夹文件 (.ost)。 您的位置. 这些设置通过使用唯一标识符 ( **pbGlobalProfileSectionGuid**属性) 进行标识。 用于 exchange 设置的部分称为 "exchange 全局配置文件" 部分。 
  
固定的配置文件部分位置已不再足以容纳多个 Exchange 帐户。 相反, 对于您的配置文件中的每个 Exchange 帐户, 都存在专用于该帐户设置的分区。 用于 Exchange 设置的新节由唯一标识符**emsmdbUID**标识。
  
在 Exchange 帐户的 "邮件服务配置文件" 部分, 您可以找到包含在创建帐户时动态生成的 GUID 的属性。 此 GUID 存储在**PidTagExchangeProfileSectionId**属性中。 邮件存储和通讯簿容器公开属性以确定其所属的 Exchange 帐户。 可在邮件服务表中访问, 每个 Exchange 服务公开此属性。 
  
在查询以下任一接口之后, 可以通过调用[IMAPIProp:: GetProps](imapiprop-getprops.md) on **PidTagExchangeProfileSectionId**检索此属性: 
  
- [IMsgStore : IMAPIProp](imsgstoreimapiprop.md)
    
- [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)
    
- [IABContainer : IMAPIContainer](iabcontainerimapicontainer.md)
    
如果该对象不是与 Exchange 关联, 则调用将返回**MAPI_E_NOT_FOUND**。
  
您可以在显示通讯簿时限制**PidTagExchangeProfileSectionId**上的容器。 打开容器后, 可以从该容器中查询**emsmdbUID** 。 也值得注意的是, 如果从 Exchange 通讯簿中选择了收件人, 则收件人的属性列表中也会包含**PidTagExchangeProfileSectionId** 。 
  
> [!NOTE]
> 在代码示例和函数头中, 此 GUID 称为 " **emsmdbUID**"。 
  
其中一个 exchange 帐户被标记为旧版 exchange 帐户。 通常情况下, 它是添加到配置文件中的第一个帐户。 对打开的**pbGlobalProfileSectionGuid**的每个调用都将重定向到旧版帐户的 Exchange 全局部分。 与非旧版 exchange 帐户交互的对象模型调用也与旧版 exchange 帐户进行交互。 
  
旧版 Exchange 服务具有属性**PR_EMSMDB_LEGACY** (0x3D18000B), 该属性在邮件服务表中设置为**true** 。 
  
旧版**emsmdbUID**也在配置文件的 "Outlook 全局配置文件" 部分中标记为 " **PidTagExchangeProfileSectionId**"。 为支持多个 Exchange 帐户而编写的代码不应检索旧版**emsmdbUID** , 因为它应获取正确的**emsmdbUID**, 具体取决于您的代码与您的代码进行交互的帐户。
  
## <a name="see-also"></a>另请参阅



[使用多个 Exchange 帐户](using-multiple-exchange-accounts.md)


[如何打开 "全局配置文件" 部分](https://support.microsoft.com/kb/188482)

