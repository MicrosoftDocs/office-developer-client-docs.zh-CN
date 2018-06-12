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
# <a name="pidtagexchangeprofilesectionid-canonical-property"></a><span data-ttu-id="91061-103">PidTagExchangeProfileSectionId 规范属性</span><span class="sxs-lookup"><span data-stu-id="91061-103">PidTagExchangeProfileSectionId Canonical Property</span></span>

  
  
<span data-ttu-id="91061-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="91061-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="91061-105">包含用于确定帐户，使用多个 Microsoft Exchange Server 帐户时动态生成的 GUID。</span><span class="sxs-lookup"><span data-stu-id="91061-105">Contains a dynamically generated GUID used to determine an account when you are using multiple Microsoft Exchange Server accounts.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="91061-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="91061-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="91061-107">PR_EMSMDB_SECTION_UID</span><span class="sxs-lookup"><span data-stu-id="91061-107">PR_EMSMDB_SECTION_UID</span></span>  <br/> |
|<span data-ttu-id="91061-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="91061-108">Identifier:</span></span>  <br/> |<span data-ttu-id="91061-109">0x3d150102</span><span class="sxs-lookup"><span data-stu-id="91061-109">0x3d150102</span></span>  <br/> |
|<span data-ttu-id="91061-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="91061-110">Data type:</span></span>  <br/> |<span data-ttu-id="91061-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="91061-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="91061-112">区域：</span><span class="sxs-lookup"><span data-stu-id="91061-112">Area:</span></span>  <br/> |<span data-ttu-id="91061-113">多个 Exchange 帐户</span><span class="sxs-lookup"><span data-stu-id="91061-113">Multiple Exchange Accounts</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="91061-114">备注</span><span class="sxs-lookup"><span data-stu-id="91061-114">Remarks</span></span>

<span data-ttu-id="91061-115">Microsoft Outlook 2010 和 Microsoft Outlook 2013 支持多个 Exchange 帐户，而不是一个一个 Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="91061-115">Microsoft Outlook 2010 and Microsoft Outlook 2013 support multiple Exchange accounts instead of one single Exchange account.</span></span> <span data-ttu-id="91061-116">若要容纳多个 Exchange 帐户，已更改的 MAPI 配置文件布局。</span><span class="sxs-lookup"><span data-stu-id="91061-116">To accommodate multiple Exchange accounts, the MAPI profile layout was changed.</span></span> <span data-ttu-id="91061-117">在 Microsoft Office Outlook 2007 和更早版本，配置文件包含专用于 Exchange 设置，如服务器名称、 用户名和脱机文件夹文件 (.ost) 固定的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="91061-117">In Microsoft Office Outlook 2007 and earlier, profiles contained a fixed profile section dedicated to Exchange settings such as server name, user name, and Offline Folder file (.ost).</span></span> <span data-ttu-id="91061-118">位置。</span><span class="sxs-lookup"><span data-stu-id="91061-118">location.</span></span> <span data-ttu-id="91061-119">使用的唯一标识符， **pbGlobalProfileSectionGuid**属性标识了这些设置。</span><span class="sxs-lookup"><span data-stu-id="91061-119">These settings were identified by using a unique identifier, the **pbGlobalProfileSectionGuid** property.</span></span> <span data-ttu-id="91061-120">用于 Exchange 设置部分称为 Exchange 全局配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="91061-120">The section used for Exchange settings is called the Exchange Global Profile Section.</span></span> <span data-ttu-id="91061-121">有关 Outlook 2007 中的 Exchange 全局配置文件的详细信息，请参阅[如何打开全局配置文件部分](http://support.microsoft.com/kb/188482)。</span><span class="sxs-lookup"><span data-stu-id="91061-121">For more information about the Exchange Global Profile in Outlook 2007, see [How To Open the Global Profile Section](http://support.microsoft.com/kb/188482).</span></span>
  
<span data-ttu-id="91061-122">固定的配置文件部分位置不再足以容纳多个 Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="91061-122">A fixed profile section location is no longer sufficient to accommodate multiple Exchange accounts.</span></span> <span data-ttu-id="91061-123">相反，您的配置文件中的每个 Exchange 帐户，节存在的专用于该帐户的设置。</span><span class="sxs-lookup"><span data-stu-id="91061-123">Instead, for each Exchange account in your profile, a section exists that is dedicated to settings for that account.</span></span> <span data-ttu-id="91061-124">由唯一标识符**emsmdbUID**标识用于 Exchange 设置新建部分。</span><span class="sxs-lookup"><span data-stu-id="91061-124">The new section used for Exchange settings is identified by the unique identifier **emsmdbUID**.</span></span>
  
<span data-ttu-id="91061-125">在消息服务配置文件的 Exchange 帐户部分，您可以找到包含在创建帐户时动态生成的 GUID 的属性。</span><span class="sxs-lookup"><span data-stu-id="91061-125">In the message service profile section for the Exchange account, you can find a property that contains a GUID that is dynamically generated at the time that the account is created.</span></span> <span data-ttu-id="91061-126">此 GUID 存储在**PidTagExchangeProfileSectionId**属性。</span><span class="sxs-lookup"><span data-stu-id="91061-126">This GUID is stored in the **PidTagExchangeProfileSectionId** property.</span></span> <span data-ttu-id="91061-127">消息存储和通讯簿容器公开属性来确定其所属的 Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="91061-127">Message stores and address book containers expose a property to determine which Exchange account they belong to.</span></span> <span data-ttu-id="91061-128">访问在消息服务表中，每个 Exchange 服务公开此属性。</span><span class="sxs-lookup"><span data-stu-id="91061-128">Accessible in the message services table, each Exchange service exposes this property.</span></span> 
  
<span data-ttu-id="91061-129">您可以在任何以下接口查询后检索通过[IMAPIProp::GetProps](imapiprop-getprops.md) **PidTagExchangeProfileSectionId**上调用此属性：</span><span class="sxs-lookup"><span data-stu-id="91061-129">You can retrieve this property through a call to [IMAPIProp::GetProps](imapiprop-getprops.md) on **PidTagExchangeProfileSectionId** after querying for any of the following interfaces:</span></span> 
  
- [<span data-ttu-id="91061-130">IMsgStore: IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="91061-130">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)
    
- [<span data-ttu-id="91061-131">IMAPIFolder: IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="91061-131">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)
    
- [<span data-ttu-id="91061-132">IABContainer: IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="91061-132">IABContainer : IMAPIContainer</span></span>](iabcontainerimapicontainer.md)
    
<span data-ttu-id="91061-133">如果对象 Exchange 未加入，呼叫将返回**MAPI_E_NOT_FOUND**。</span><span class="sxs-lookup"><span data-stu-id="91061-133">If the object is not affiliated with Exchange, the call returns **MAPI_E_NOT_FOUND**.</span></span>
  
<span data-ttu-id="91061-134">显示通讯簿时，您可以限制对**PidTagExchangeProfileSectionId**的容器。</span><span class="sxs-lookup"><span data-stu-id="91061-134">You can restrict containers on a **PidTagExchangeProfileSectionId** when displaying the address book.</span></span> <span data-ttu-id="91061-135">打开的容器后，您可以查询从其**emsmdbUID** 。</span><span class="sxs-lookup"><span data-stu-id="91061-135">Once you have an opened container, you can query the **emsmdbUID** from it.</span></span> <span data-ttu-id="91061-136">也是值得注意的 Exchange 通讯簿中选择收件人，是否收件人也有**PidTagExchangeProfileSectionId**属性及其列表中。</span><span class="sxs-lookup"><span data-stu-id="91061-136">It is also worth noting that if a recipient was selected from an Exchange address book, the recipient also has the **PidTagExchangeProfileSectionId** in its list of properties.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="91061-137">在整个代码示例和函数标头，此 GUID 称为**emsmdbUID**。</span><span class="sxs-lookup"><span data-stu-id="91061-137">Throughout the code samples and function headers, this GUID is known as **emsmdbUID**.</span></span> 
  
<span data-ttu-id="91061-138">一个 Exchange 帐户标记为旧版的 Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="91061-138">One of the Exchange accounts is marked as the legacy Exchange account.</span></span> <span data-ttu-id="91061-139">通常，它是添加到配置文件的第一个帐户。</span><span class="sxs-lookup"><span data-stu-id="91061-139">Usually, it is the first account added to the profile.</span></span> <span data-ttu-id="91061-140">打开**pbGlobalProfileSectionGuid**每个呼叫将重定向到 Exchange 的旧帐户的全局部分。</span><span class="sxs-lookup"><span data-stu-id="91061-140">Every call to open **pbGlobalProfileSectionGuid** is redirected to the Exchange global section of the legacy account.</span></span> <span data-ttu-id="91061-141">与非旧式 Exchange 帐户进行交互的对象模型调用还交互旧式 Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="91061-141">The object model calls that interact with the non-legacy Exchange account also interact with the legacy Exchange account.</span></span> 
  
<span data-ttu-id="91061-142">旧版的 Exchange 服务具有**PR_EMSMDB_LEGACY** (0x3D18000B)，其设置为**true**消息服务表中的属性。</span><span class="sxs-lookup"><span data-stu-id="91061-142">The legacy Exchange service has the property **PR_EMSMDB_LEGACY** (0x3D18000B), which is set to **true** in the message services table.</span></span> 
  
<span data-ttu-id="91061-143">旧**emsmdbUID**是还标在配置文件的 Outlook 全局配置文件部分为**PidTagExchangeProfileSectionId**。</span><span class="sxs-lookup"><span data-stu-id="91061-143">The legacy **emsmdbUID** is also stamped in the Outlook Global Profile Section of the profile as **PidTagExchangeProfileSectionId**.</span></span> <span data-ttu-id="91061-144">代码编写为支持多个 Exchange 帐户不应包含要检索旧**emsmdbUID** ，因为它应获取正确**emsmdbUID**，具体取决于您的代码与之交互的帐户。</span><span class="sxs-lookup"><span data-stu-id="91061-144">Code written to support multiple Exchange accounts should not have to retrieve the legacy **emsmdbUID** because it should get the correct **emsmdbUID**, depending on the account your code is interacting with.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="91061-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91061-145">See also</span></span>



[<span data-ttu-id="91061-146">使用多个 Exchange 帐户</span><span class="sxs-lookup"><span data-stu-id="91061-146">Using Multiple Exchange Accounts</span></span>](using-multiple-exchange-accounts.md)


[<span data-ttu-id="91061-147">如何打开全局配置文件部分</span><span class="sxs-lookup"><span data-stu-id="91061-147">How To Open the Global Profile Section</span></span>](http://support.microsoft.com/kb/188482)

