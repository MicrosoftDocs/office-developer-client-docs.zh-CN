---
title: PidLidInternetAccountName
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 5acca047-ff2a-716c-8dd4-b676fce1a3cf
description: 返回传递邮件的帐户的显示名称。
ms.openlocfilehash: 2bd27cc7f868fb3f255a002ed70d0cb9b79516e3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327683"
---
# <a name="pidlidinternetaccountname"></a>PidLidInternetAccountName

返回传递邮件的帐户的显示名称。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|相关属性：  <br/> |dispidInetAcctName  <br/> |
|属性集:  <br/> |PSETID_Common  <br/> |
|长 ID (盖子):  <br/> |0x00008580  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |常规邮件  <br/> |
   
## <a name="remarks"></a>注解

此属性应包含的值与传递邮件的帐户的帐户管理 API 属性[PROP_ACCT_NAME](prop_acct_name.md)返回的值相同。 
  
邮件存储提供程序公开此命名属性和[PidLidInternetAccountStamp](pidlidinternetaccountstamp.md) , 以便执行以下操作: 
  
- 当用户单击电子邮件中的 "**全部答复**" 时, Outlook 将删除与该帐户关联的电子邮件地址, 并将其标记为答复邮件的收件人列表中的邮件。 如果此电子邮件地址是原始邮件的发件人, 则会出现此行为。 
    
- 默认情况下, Outlook 通过原始邮件上标记的帐户发送答复邮件和转发邮件。
    
通常情况下, outlook 协议管理器会传递邮件, outlook 会设置**PidLidInternetAccountName**和**PidLidInternetAccountStamp**属性, 以指示传递邮件的帐户。 但是, 如果邮件存储与传输紧密结合, outlook 协议管理器将不传递邮件, 并且 outlook 无法设置这些属性。 在这种情况下, Outlook 将调用[IMAPIProp:: GetIDsFromNames](https://msdn.microsoft.com/library/e3f501a4-a8ee-43d7-bd83-c94e7980c398%28Office.15%29.aspx)函数。 如果邮件存储区提供程序想要公开这些命名属性, 它应通过 output parameter *lppPropTags*实现**IMAPIProp:: GetIDsFromNames**和返回属性标记。 然后, Outlook 可以使用这些属性标记调用[IMAPIProp:: GetProps](https://msdn.microsoft.com/library/1c7a9cd2-d765-4218-9aee-52df1a2aae6c%28Office.15%29.aspx)方法, 邮件存储区提供程序可以返回所需帐户的帐户名称和 stamp。 
  
若要支持这些命名属性, 存储提供程序应期望 Outlook 使用**IMAPIProp:: GetIDsFromNames**获取此属性的属性标记。 Outlook 指定与此命名属性对应的[MAPINAMEID](https://msdn.microsoft.com/library/9a92e9cd-8282-4cf0-93af-4089b3763594%28Office.15%29.aspx)结构的以下值, 该属性作为由**IMAPIProp:: GetIDsFromNames**的输入参数*lppPropNames*所指向的数组的一部分进行传递。 
  
|||
|:-----|:-----|
|lpGuid:  <br/> |PSETID_Common  <br/> |
|ulKind:  <br/> |MNID_ID  <br/> |
|类型盖子:  <br/> |dispidInetAcctName  <br/> |
   
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)
- [常量 （帐户管理 API）](constants-account-management-api.md)
- [PidLidInternetAccountName 规范属性](https://msdn.microsoft.com/library/29bedadf-903d-419d-804d-dc8bd92b745d%28Office.15%29.aspx)

