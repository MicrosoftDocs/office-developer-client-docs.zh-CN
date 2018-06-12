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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 37a318df01101487fe0e8970251201c2515d1e8a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777591"
---
# <a name="pidtagexchangeprofilesectionid-canonical-property"></a>PidTagExchangeProfileSectionId 规范属性

  
  
**适用于**： Outlook 
  
包含用于确定帐户，使用多个 Microsoft Exchange Server 帐户时动态生成的 GUID。
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_EMSMDB_SECTION_UID  <br/> |
|标识符:  <br/> |0x3d150102  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |多个 Exchange 帐户  <br/> |
   
## <a name="remarks"></a>备注

Microsoft Outlook 2010 和 Microsoft Outlook 2013 支持多个 Exchange 帐户，而不是一个一个 Exchange 帐户。 若要容纳多个 Exchange 帐户，已更改的 MAPI 配置文件布局。 在 Microsoft Office Outlook 2007 和更早版本，配置文件包含专用于 Exchange 设置，如服务器名称、 用户名和脱机文件夹文件 (.ost) 固定的配置文件部分。 位置。 使用的唯一标识符， **pbGlobalProfileSectionGuid**属性标识了这些设置。 用于 Exchange 设置部分称为 Exchange 全局配置文件部分。 有关 Outlook 2007 中的 Exchange 全局配置文件的详细信息，请参阅[如何打开全局配置文件部分](http://support.microsoft.com/kb/188482)。
  
固定的配置文件部分位置不再足以容纳多个 Exchange 帐户。 相反，您的配置文件中的每个 Exchange 帐户，节存在的专用于该帐户的设置。 由唯一标识符**emsmdbUID**标识用于 Exchange 设置新建部分。
  
在消息服务配置文件的 Exchange 帐户部分，您可以找到包含在创建帐户时动态生成的 GUID 的属性。 此 GUID 存储在**PidTagExchangeProfileSectionId**属性。 消息存储和通讯簿容器公开属性来确定其所属的 Exchange 帐户。 访问在消息服务表中，每个 Exchange 服务公开此属性。 
  
您可以在任何以下接口查询后检索通过[IMAPIProp::GetProps](imapiprop-getprops.md) **PidTagExchangeProfileSectionId**上调用此属性： 
  
- [IMsgStore: IMAPIProp](imsgstoreimapiprop.md)
    
- [IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)
    
- [IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)
    
如果对象 Exchange 未加入，呼叫将返回**MAPI_E_NOT_FOUND**。
  
显示通讯簿时，您可以限制对**PidTagExchangeProfileSectionId**的容器。 打开的容器后，您可以查询从其**emsmdbUID** 。 也是值得注意的 Exchange 通讯簿中选择收件人，是否收件人也有**PidTagExchangeProfileSectionId**属性及其列表中。 
  
> [!NOTE]
> 在整个代码示例和函数标头，此 GUID 称为**emsmdbUID**。 
  
一个 Exchange 帐户标记为旧版的 Exchange 帐户。 通常，它是添加到配置文件的第一个帐户。 打开**pbGlobalProfileSectionGuid**每个呼叫将重定向到 Exchange 的旧帐户的全局部分。 与非旧式 Exchange 帐户进行交互的对象模型调用还交互旧式 Exchange 帐户。 
  
旧版的 Exchange 服务具有**PR_EMSMDB_LEGACY** (0x3D18000B)，其设置为**true**消息服务表中的属性。 
  
旧**emsmdbUID**是还标在配置文件的 Outlook 全局配置文件部分为**PidTagExchangeProfileSectionId**。 代码编写为支持多个 Exchange 帐户不应包含要检索旧**emsmdbUID** ，因为它应获取正确**emsmdbUID**，具体取决于您的代码与之交互的帐户。
  
## <a name="see-also"></a>另请参阅



[使用多个 Exchange 帐户](using-multiple-exchange-accounts.md)


[如何打开全局配置文件部分](http://support.microsoft.com/kb/188482)

