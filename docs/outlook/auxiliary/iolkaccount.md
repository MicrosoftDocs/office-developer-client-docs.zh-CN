---
title: IOlkAccount
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7b7cb295-fc77-a8b9-aac9-e548f3b4afcb
ms.openlocfilehash: 007a44d13565889b4775f2d3fe9979685e1878b3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425062"
---
# <a name="iolkaccount"></a><span data-ttu-id="3e590-102">IOlkAccount</span><span class="sxs-lookup"><span data-stu-id="3e590-102">IOlkAccount</span></span>

<span data-ttu-id="3e590-103">支持获取和设置属性以及帐户的其他信息。</span><span class="sxs-lookup"><span data-stu-id="3e590-103">Supports getting and setting of properties and other information about an account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="3e590-104">快速信息</span><span class="sxs-lookup"><span data-stu-id="3e590-104">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3e590-105">继承自：</span><span class="sxs-lookup"><span data-stu-id="3e590-105">Inherits from:</span></span>  <br/> |[<span data-ttu-id="3e590-106">IOlkErrorUnknown</span><span class="sxs-lookup"><span data-stu-id="3e590-106">IOlkErrorUnknown</span></span>](iolkerrorunknown.md) <br/> |
|<span data-ttu-id="3e590-107">实现者：</span><span class="sxs-lookup"><span data-stu-id="3e590-107">Implemented by:</span></span>  <br/> |<span data-ttu-id="3e590-108">Outlook</span><span class="sxs-lookup"><span data-stu-id="3e590-108">Outlook</span></span>  <br/> |
|<span data-ttu-id="3e590-109">提供者：</span><span class="sxs-lookup"><span data-stu-id="3e590-109">Provided by:</span></span>  <br/> |<span data-ttu-id="3e590-110">[IOlkAccountManager：：FindAccount](iolkaccountmanager-findaccount.md) 和 [IOlkEnum：：GetNext](iolkenum-getnext.md)</span><span class="sxs-lookup"><span data-stu-id="3e590-110">[IOlkAccountManager::FindAccount](iolkaccountmanager-findaccount.md) and [IOlkEnum::GetNext](iolkenum-getnext.md)</span></span> <br/> |
|<span data-ttu-id="3e590-111">调用者：</span><span class="sxs-lookup"><span data-stu-id="3e590-111">Called by:</span></span>  <br/> |<span data-ttu-id="3e590-112">客户端</span><span class="sxs-lookup"><span data-stu-id="3e590-112">Client</span></span>  <br/> |
|<span data-ttu-id="3e590-113">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="3e590-113">Interface identifier:</span></span>  <br/> |<span data-ttu-id="3e590-114">IID_IOlkAccount</span><span class="sxs-lookup"><span data-stu-id="3e590-114">IID_IOlkAccount</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="3e590-115">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="3e590-115">Vtable order</span></span>

|||
|:-----|:-----|
| <span data-ttu-id="3e590-116">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="3e590-116">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="3e590-117">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="3e590-117">*Not supported or documented.*</span></span>  <br/> |
| <span data-ttu-id="3e590-118">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="3e590-118">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="3e590-119">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="3e590-119">*Not supported or documented.*</span></span>  <br/> |
| <span data-ttu-id="3e590-120">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="3e590-120">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="3e590-121">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="3e590-121">*Not supported or documented.*</span></span>  <br/> |
| <span data-ttu-id="3e590-122">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="3e590-122">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="3e590-123">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="3e590-123">*Not supported or documented.*</span></span>  <br/> |
| <span data-ttu-id="3e590-124">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="3e590-124">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="3e590-125">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="3e590-125">*Not supported or documented.*</span></span>  <br/> |
| <span data-ttu-id="3e590-126">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="3e590-126">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="3e590-127">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="3e590-127">*Not supported or documented.*</span></span>  <br/> |
|[<span data-ttu-id="3e590-128">GetAccountInfo</span><span class="sxs-lookup"><span data-stu-id="3e590-128">GetAccountInfo</span></span>](iolkaccount-getaccountinfo.md) <br/> |<span data-ttu-id="3e590-129">获取指定帐户的类型和类别。</span><span class="sxs-lookup"><span data-stu-id="3e590-129">Gets the type and categories of the specified account.</span></span>  <br/> |
|[<span data-ttu-id="3e590-130">GetProp</span><span class="sxs-lookup"><span data-stu-id="3e590-130">GetProp</span></span>](iolkaccount-getprop.md) <br/> |<span data-ttu-id="3e590-131">获取指定帐户属性的值。</span><span class="sxs-lookup"><span data-stu-id="3e590-131">Gets the value of the specified account property.</span></span> <span data-ttu-id="3e590-132">请参阅下面的"属性"表。</span><span class="sxs-lookup"><span data-stu-id="3e590-132">See the Properties table below.</span></span>  <br/> |
|[<span data-ttu-id="3e590-133">SetProp</span><span class="sxs-lookup"><span data-stu-id="3e590-133">SetProp</span></span>](iolkaccount-setprop.md) <br/> |<span data-ttu-id="3e590-134">设置指定帐户属性的值。</span><span class="sxs-lookup"><span data-stu-id="3e590-134">Sets the value of the specified account property.</span></span> <span data-ttu-id="3e590-135">请参阅下面的"属性"表。</span><span class="sxs-lookup"><span data-stu-id="3e590-135">See the Properties table below.</span></span>  <br/> |
| <span data-ttu-id="3e590-136">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="3e590-136">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="3e590-137">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="3e590-137">*Not supported or documented.*</span></span>  <br/> |
| <span data-ttu-id="3e590-138">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="3e590-138">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="3e590-139">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="3e590-139">*Not supported or documented.*</span></span>  <br/> |
| <span data-ttu-id="3e590-140">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="3e590-140">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="3e590-141">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="3e590-141">*Not supported or documented.*</span></span>  <br/> |
|[<span data-ttu-id="3e590-142">FreeMemory</span><span class="sxs-lookup"><span data-stu-id="3e590-142">FreeMemory</span></span>](iolkaccount-freememory.md) <br/> |<span data-ttu-id="3e590-143">释放由 **IOlkAccount** 接口分配的内存。</span><span class="sxs-lookup"><span data-stu-id="3e590-143">Frees memory allocated by the **IOlkAccount** interface.</span></span>  <br/> |
| <span data-ttu-id="3e590-144">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="3e590-144">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="3e590-145">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="3e590-145">*Not supported or documented.*</span></span>  <br/> |
|[<span data-ttu-id="3e590-146">SaveChanges</span><span class="sxs-lookup"><span data-stu-id="3e590-146">SaveChanges</span></span>](iolkaccount-savechanges.md) <br/> |<span data-ttu-id="3e590-147">通过写入注册表存储来提交对帐户对象的更改。</span><span class="sxs-lookup"><span data-stu-id="3e590-147">Commits changes to the account object by writing to the registry store.</span></span>  <br/> |
   
## <a name="properties"></a><span data-ttu-id="3e590-148">属性</span><span class="sxs-lookup"><span data-stu-id="3e590-148">Properties</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="3e590-149">PROP_ACCT_DELIVERY_FOLDER</span><span class="sxs-lookup"><span data-stu-id="3e590-149">PROP_ACCT_DELIVERY_FOLDER</span></span>](prop_acct_delivery_folder.md) <br/> |<span data-ttu-id="3e590-150">表示该帐户的默认送达文件夹的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="3e590-150">Represents the Entry ID of the default delivery folder for the account.</span></span>  <br/> |
|[<span data-ttu-id="3e590-151">PROP_ACCT_DELIVERY_STORE</span><span class="sxs-lookup"><span data-stu-id="3e590-151">PROP_ACCT_DELIVERY_STORE</span></span>](prop_acct_delivery_store.md) <br/> |<span data-ttu-id="3e590-152">表示帐户的默认送达存储的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="3e590-152">Represents the Entry ID of the default delivery store for the account.</span></span>  <br/> |
|[<span data-ttu-id="3e590-153">PROP_ACCT_ID</span><span class="sxs-lookup"><span data-stu-id="3e590-153">PROP_ACCT_ID</span></span>](prop_acct_id.md) <br/> |<span data-ttu-id="3e590-154">返回 Outlook 2000 及早期版本的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="3e590-154">Returns the account identifier in Outlook 2000 and earlier versions of Outlook.</span></span>  <br/> |
|[<span data-ttu-id="3e590-155">PROP_ACCT_IS_EXCH</span><span class="sxs-lookup"><span data-stu-id="3e590-155">PROP_ACCT_IS_EXCH</span></span>](prop_acct_is_exch.md) <br/> |<span data-ttu-id="3e590-156">如此 如果该帐户是 Microsoft Exchange帐户。</span><span class="sxs-lookup"><span data-stu-id="3e590-156">True if the account is a Microsoft Exchange account.</span></span>  <br/> |
|[<span data-ttu-id="3e590-157">PROP_ACCT_MINI_UID</span><span class="sxs-lookup"><span data-stu-id="3e590-157">PROP_ACCT_MINI_UID</span></span>](prop_acct_mini_uid.md) <br/> |<span data-ttu-id="3e590-158">返回自 2002 Outlook以来Outlook帐户标识符。</span><span class="sxs-lookup"><span data-stu-id="3e590-158">Returns the account identifier in versions of Outlook since Outlook 2002.</span></span>  <br/> |
|[<span data-ttu-id="3e590-159">PROP_ACCT_NAME</span><span class="sxs-lookup"><span data-stu-id="3e590-159">PROP_ACCT_NAME</span></span>](prop_acct_name.md) <br/> |<span data-ttu-id="3e590-160">返回帐户名称。</span><span class="sxs-lookup"><span data-stu-id="3e590-160">Returns the account name.</span></span>  <br/> |
|[<span data-ttu-id="3e590-161">PROP_ACCT_PREFERENCES_UID</span><span class="sxs-lookup"><span data-stu-id="3e590-161">PROP_ACCT_PREFERENCES_UID</span></span>](prop_acct_preferences_uid.md) <br/> |<span data-ttu-id="3e590-162">检索存储帐户首选项 (配置文件) UID 对象的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="3e590-162">Retrieves the unique identifier (UID) for the profile section that stores the account preferences.</span></span>  <br/> |
|[<span data-ttu-id="3e590-163">PROP_ACCT_SEND_STAMP</span><span class="sxs-lookup"><span data-stu-id="3e590-163">PROP_ACCT_SEND_STAMP</span></span>](prop_acct_send_stamp.md) <br/> |<span data-ttu-id="3e590-164">返回帐户"send"标记。</span><span class="sxs-lookup"><span data-stu-id="3e590-164">Returns the account "send" stamp.</span></span>  <br/> |
|[<span data-ttu-id="3e590-165">PROP_ACCT_SENTITEMS_EID</span><span class="sxs-lookup"><span data-stu-id="3e590-165">PROP_ACCT_SENTITEMS_EID</span></span>](prop_acct_sentitems_eid.md) <br/> |<span data-ttu-id="3e590-166">表示帐户已发送项目的默认文件夹的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="3e590-166">Represents the Entry ID of the default folder for sent items for the account.</span></span>  <br/> |
|[<span data-ttu-id="3e590-167">PROP_ACCT_STAMP</span><span class="sxs-lookup"><span data-stu-id="3e590-167">PROP_ACCT_STAMP</span></span>](prop_acct_stamp.md) <br/> |<span data-ttu-id="3e590-168">返回帐户标记。</span><span class="sxs-lookup"><span data-stu-id="3e590-168">Returns the account stamp.</span></span>  <br/> |
|[<span data-ttu-id="3e590-169">PROP_ACCT_USER_DISPLAY_NAME</span><span class="sxs-lookup"><span data-stu-id="3e590-169">PROP_ACCT_USER_DISPLAY_NAME</span></span>](prop_acct_user_display_name.md) <br/> |<span data-ttu-id="3e590-170">返回用户显示名称。</span><span class="sxs-lookup"><span data-stu-id="3e590-170">Returns the user display name.</span></span>  <br/> |
|[<span data-ttu-id="3e590-171">PROP_ACCT_USER_EMAIL_ADDR</span><span class="sxs-lookup"><span data-stu-id="3e590-171">PROP_ACCT_USER_EMAIL_ADDR</span></span>](prop_acct_user_email_addr.md) <br/> |<span data-ttu-id="3e590-172">指定帐户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3e590-172">Specifies the email address for the account.</span></span>  <br/> |
|[<span data-ttu-id="3e590-173">PROP_MAPI_EMSMDB_UID</span><span class="sxs-lookup"><span data-stu-id="3e590-173">PROP_MAPI_EMSMDB_UID</span></span>](prop_mapi_emsmdb_uid.md) <br/> |<span data-ttu-id="3e590-174">表示[ACCT_BIN](acct_bin.md)帐户的 UID 的 Exchange 结构。</span><span class="sxs-lookup"><span data-stu-id="3e590-174">Represents an [ACCT_BIN](acct_bin.md) structure that contains the UID of an Exchange account.</span></span>  <br/> |
|[<span data-ttu-id="3e590-175">PROP_MAPI_IDENTITY_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="3e590-175">PROP_MAPI_IDENTITY_ENTRYID</span></span>](prop_mapi_identity_entryid.md) <br/> |<span data-ttu-id="3e590-176">检索或设置帐户的通讯簿条目 ID。</span><span class="sxs-lookup"><span data-stu-id="3e590-176">Retrieves or sets the address book entry ID for the account.</span></span>  <br/> |
|[<span data-ttu-id="3e590-177">PROP_MAPI_TRANSPORT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="3e590-177">PROP_MAPI_TRANSPORT_FLAGS</span></span>](prop_mapi_transport_flags.md) <br/> |<span data-ttu-id="3e590-178">表示 Microsoft Outlook用于确定必要的同步任务和禁用用户界面 (UI) 帐户不支持的元素的传输设置。</span><span class="sxs-lookup"><span data-stu-id="3e590-178">Represents transport settings that Microsoft Outlook uses to determine the necessary synchronization tasks and to disable the user interface (UI) elements that the account does not support.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3e590-179">备注</span><span class="sxs-lookup"><span data-stu-id="3e590-179">Remarks</span></span>

<span data-ttu-id="3e590-180">当在枚举器中查找支持 **IOlkAccount** 和 **IOlkEnum：：GetNext** 的帐户时 **，IOlkAccountManager：：FindAccount** 将返回此接口。</span><span class="sxs-lookup"><span data-stu-id="3e590-180">This interface is returned by **IOlkAccountManager::FindAccount** when searching for an account that supports **IOlkAccount** and **IOlkEnum::GetNext** when getting the next account in an enumerator.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3e590-181">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e590-181">See also</span></span>

- [<span data-ttu-id="3e590-182">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="3e590-182">About the Account Management API</span></span>](about-the-account-management-api.md)  
- [<span data-ttu-id="3e590-183">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="3e590-183">Constants (Account management API)</span></span>](constants-account-management-api.md)

