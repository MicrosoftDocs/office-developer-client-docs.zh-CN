---
title: ChangePassword 方法 (ADOX)
TOCTitle: ChangePassword method (ADOX)
ms:assetid: 999826a5-3e6b-b6da-b8f6-d61b9a50ceca
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249690(v=office.15)
ms:contentKeyID: 48546519
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: df67774b9b38b5fbcc836a2ea0dfc17886d67107
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296526"
---
# <a name="changepassword-method-adox"></a><span data-ttu-id="6e723-102">ChangePassword 方法 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="6e723-102">ChangePassword method (ADOX)</span></span>

<span data-ttu-id="6e723-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="6e723-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6e723-104">更改用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="6e723-104">Changes the password for a user account.</span></span>

## <a name="syntax"></a><span data-ttu-id="6e723-105">语法</span><span class="sxs-lookup"><span data-stu-id="6e723-105">Syntax</span></span>

<span data-ttu-id="6e723-106">*用户*。ChangePassword*OldPassword*, *NewPassword*</span><span class="sxs-lookup"><span data-stu-id="6e723-106">*User*.ChangePassword*OldPassword*, *NewPassword*</span></span>

## <a name="parameters"></a><span data-ttu-id="6e723-107">参数</span><span class="sxs-lookup"><span data-stu-id="6e723-107">Parameters</span></span>

|<span data-ttu-id="6e723-108">参数</span><span class="sxs-lookup"><span data-stu-id="6e723-108">Parameter</span></span>|<span data-ttu-id="6e723-109">描述</span><span class="sxs-lookup"><span data-stu-id="6e723-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="6e723-110">*OldPassword*</span><span class="sxs-lookup"><span data-stu-id="6e723-110">*OldPassword*</span></span> |<span data-ttu-id="6e723-111">一个指定用户现有密码的 **String** 值。</span><span class="sxs-lookup"><span data-stu-id="6e723-111">A **String** value that specifies the user's existing password.</span></span> <span data-ttu-id="6e723-112">如果该用户当前没有密码，则使用空字符串 ("") 作为 *OldPassword*。</span><span class="sxs-lookup"><span data-stu-id="6e723-112">If the user doesn't currently have a password, use an empty string ("") for *OldPassword*.</span></span>|
|<span data-ttu-id="6e723-113">*NewPassword*</span><span class="sxs-lookup"><span data-stu-id="6e723-113">*NewPassword*</span></span> |<span data-ttu-id="6e723-114">一个指定新密码的 **String** 值。</span><span class="sxs-lookup"><span data-stu-id="6e723-114">A **String** value that specifies the new password.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6e723-115">注解</span><span class="sxs-lookup"><span data-stu-id="6e723-115">Remarks</span></span>

<span data-ttu-id="6e723-116">出于安全原因，除了新密码之外还必须指定旧密码。</span><span class="sxs-lookup"><span data-stu-id="6e723-116">For security reasons, the old password must be specified in addition to the new password.</span></span>

<span data-ttu-id="6e723-117">如果提供程序不支持管理受任者属性，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="6e723-117">An error will occur if the provider does not support the administration of trustee properties.</span></span>

