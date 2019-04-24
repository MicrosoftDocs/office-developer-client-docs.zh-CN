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
# <a name="pidtagexchangeprofilesectionid-canonical-property"></a><span data-ttu-id="a0e5d-103">PidTagExchangeProfileSectionId 规范属性</span><span class="sxs-lookup"><span data-stu-id="a0e5d-103">PidTagExchangeProfileSectionId Canonical Property</span></span>

  
  
<span data-ttu-id="a0e5d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a0e5d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a0e5d-105">包含在使用多个 Microsoft Exchange Server 帐户时用于确定帐户的动态生成的 GUID。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-105">Contains a dynamically generated GUID used to determine an account when you are using multiple Microsoft Exchange Server accounts.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a0e5d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a0e5d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a0e5d-107">PR_EMSMDB_SECTION_UID</span><span class="sxs-lookup"><span data-stu-id="a0e5d-107">PR_EMSMDB_SECTION_UID</span></span>  <br/> |
|<span data-ttu-id="a0e5d-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="a0e5d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a0e5d-109">0x3d150102</span><span class="sxs-lookup"><span data-stu-id="a0e5d-109">0x3d150102</span></span>  <br/> |
|<span data-ttu-id="a0e5d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a0e5d-110">Data type:</span></span>  <br/> |<span data-ttu-id="a0e5d-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="a0e5d-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="a0e5d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a0e5d-112">Area:</span></span>  <br/> |<span data-ttu-id="a0e5d-113">多个 Exchange 帐户</span><span class="sxs-lookup"><span data-stu-id="a0e5d-113">Multiple Exchange Accounts</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a0e5d-114">注解</span><span class="sxs-lookup"><span data-stu-id="a0e5d-114">Remarks</span></span>

<span data-ttu-id="a0e5d-115">microsoft outlook 2010 和 microsoft outlook 2013 支持多个 exchange 帐户, 而不是一个 exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-115">Microsoft Outlook 2010 and Microsoft Outlook 2013 support multiple Exchange accounts instead of one single Exchange account.</span></span> <span data-ttu-id="a0e5d-116">为了适应多个 Exchange 帐户, MAPI 配置文件的布局已更改。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-116">To accommodate multiple Exchange accounts, the MAPI profile layout was changed.</span></span> <span data-ttu-id="a0e5d-117">在 Microsoft Office Outlook 2007 及更低版本中, 配置文件包含专用于 Exchange 设置的固定配置文件部分, 如服务器名称、用户名和脱机文件夹文件 (.ost)。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-117">In Microsoft Office Outlook 2007 and earlier, profiles contained a fixed profile section dedicated to Exchange settings such as server name, user name, and Offline Folder file (.ost).</span></span> <span data-ttu-id="a0e5d-118">您的位置.</span><span class="sxs-lookup"><span data-stu-id="a0e5d-118">location.</span></span> <span data-ttu-id="a0e5d-119">这些设置通过使用唯一标识符 ( **pbGlobalProfileSectionGuid**属性) 进行标识。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-119">These settings were identified by using a unique identifier, the **pbGlobalProfileSectionGuid** property.</span></span> <span data-ttu-id="a0e5d-120">用于 exchange 设置的部分称为 "exchange 全局配置文件" 部分。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-120">The section used for Exchange settings is called the Exchange Global Profile Section.</span></span> 
  
<span data-ttu-id="a0e5d-121">固定的配置文件部分位置已不再足以容纳多个 Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-121">A fixed profile section location is no longer sufficient to accommodate multiple Exchange accounts.</span></span> <span data-ttu-id="a0e5d-122">相反, 对于您的配置文件中的每个 Exchange 帐户, 都存在专用于该帐户设置的分区。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-122">Instead, for each Exchange account in your profile, a section exists that is dedicated to settings for that account.</span></span> <span data-ttu-id="a0e5d-123">用于 Exchange 设置的新节由唯一标识符**emsmdbUID**标识。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-123">The new section used for Exchange settings is identified by the unique identifier **emsmdbUID**.</span></span>
  
<span data-ttu-id="a0e5d-124">在 Exchange 帐户的 "邮件服务配置文件" 部分, 您可以找到包含在创建帐户时动态生成的 GUID 的属性。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-124">In the message service profile section for the Exchange account, you can find a property that contains a GUID that is dynamically generated at the time that the account is created.</span></span> <span data-ttu-id="a0e5d-125">此 GUID 存储在**PidTagExchangeProfileSectionId**属性中。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-125">This GUID is stored in the **PidTagExchangeProfileSectionId** property.</span></span> <span data-ttu-id="a0e5d-126">邮件存储和通讯簿容器公开属性以确定其所属的 Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-126">Message stores and address book containers expose a property to determine which Exchange account they belong to.</span></span> <span data-ttu-id="a0e5d-127">可在邮件服务表中访问, 每个 Exchange 服务公开此属性。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-127">Accessible in the message services table, each Exchange service exposes this property.</span></span> 
  
<span data-ttu-id="a0e5d-128">在查询以下任一接口之后, 可以通过调用[IMAPIProp:: GetProps](imapiprop-getprops.md) on **PidTagExchangeProfileSectionId**检索此属性:</span><span class="sxs-lookup"><span data-stu-id="a0e5d-128">You can retrieve this property through a call to [IMAPIProp::GetProps](imapiprop-getprops.md) on **PidTagExchangeProfileSectionId** after querying for any of the following interfaces:</span></span> 
  
- [<span data-ttu-id="a0e5d-129">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="a0e5d-129">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)
    
- [<span data-ttu-id="a0e5d-130">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="a0e5d-130">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)
    
- [<span data-ttu-id="a0e5d-131">IABContainer : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="a0e5d-131">IABContainer : IMAPIContainer</span></span>](iabcontainerimapicontainer.md)
    
<span data-ttu-id="a0e5d-132">如果该对象不是与 Exchange 关联, 则调用将返回**MAPI_E_NOT_FOUND**。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-132">If the object is not affiliated with Exchange, the call returns **MAPI_E_NOT_FOUND**.</span></span>
  
<span data-ttu-id="a0e5d-133">您可以在显示通讯簿时限制**PidTagExchangeProfileSectionId**上的容器。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-133">You can restrict containers on a **PidTagExchangeProfileSectionId** when displaying the address book.</span></span> <span data-ttu-id="a0e5d-134">打开容器后, 可以从该容器中查询**emsmdbUID** 。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-134">Once you have an opened container, you can query the **emsmdbUID** from it.</span></span> <span data-ttu-id="a0e5d-135">也值得注意的是, 如果从 Exchange 通讯簿中选择了收件人, 则收件人的属性列表中也会包含**PidTagExchangeProfileSectionId** 。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-135">It is also worth noting that if a recipient was selected from an Exchange address book, the recipient also has the **PidTagExchangeProfileSectionId** in its list of properties.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a0e5d-136">在代码示例和函数头中, 此 GUID 称为 " **emsmdbUID**"。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-136">Throughout the code samples and function headers, this GUID is known as **emsmdbUID**.</span></span> 
  
<span data-ttu-id="a0e5d-137">其中一个 exchange 帐户被标记为旧版 exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-137">One of the Exchange accounts is marked as the legacy Exchange account.</span></span> <span data-ttu-id="a0e5d-138">通常情况下, 它是添加到配置文件中的第一个帐户。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-138">Usually, it is the first account added to the profile.</span></span> <span data-ttu-id="a0e5d-139">对打开的**pbGlobalProfileSectionGuid**的每个调用都将重定向到旧版帐户的 Exchange 全局部分。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-139">Every call to open **pbGlobalProfileSectionGuid** is redirected to the Exchange global section of the legacy account.</span></span> <span data-ttu-id="a0e5d-140">与非旧版 exchange 帐户交互的对象模型调用也与旧版 exchange 帐户进行交互。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-140">The object model calls that interact with the non-legacy Exchange account also interact with the legacy Exchange account.</span></span> 
  
<span data-ttu-id="a0e5d-141">旧版 Exchange 服务具有属性**PR_EMSMDB_LEGACY** (0x3D18000B), 该属性在邮件服务表中设置为**true** 。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-141">The legacy Exchange service has the property **PR_EMSMDB_LEGACY** (0x3D18000B), which is set to **true** in the message services table.</span></span> 
  
<span data-ttu-id="a0e5d-142">旧版**emsmdbUID**也在配置文件的 "Outlook 全局配置文件" 部分中标记为 " **PidTagExchangeProfileSectionId**"。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-142">The legacy **emsmdbUID** is also stamped in the Outlook Global Profile Section of the profile as **PidTagExchangeProfileSectionId**.</span></span> <span data-ttu-id="a0e5d-143">为支持多个 Exchange 帐户而编写的代码不应检索旧版**emsmdbUID** , 因为它应获取正确的**emsmdbUID**, 具体取决于您的代码与您的代码进行交互的帐户。</span><span class="sxs-lookup"><span data-stu-id="a0e5d-143">Code written to support multiple Exchange accounts should not have to retrieve the legacy **emsmdbUID** because it should get the correct **emsmdbUID**, depending on the account your code is interacting with.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a0e5d-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0e5d-144">See also</span></span>



[<span data-ttu-id="a0e5d-145">使用多个 Exchange 帐户</span><span class="sxs-lookup"><span data-stu-id="a0e5d-145">Using Multiple Exchange Accounts</span></span>](using-multiple-exchange-accounts.md)


[<span data-ttu-id="a0e5d-146">如何打开 "全局配置文件" 部分</span><span class="sxs-lookup"><span data-stu-id="a0e5d-146">How To Open the Global Profile Section</span></span>](https://support.microsoft.com/kb/188482)

