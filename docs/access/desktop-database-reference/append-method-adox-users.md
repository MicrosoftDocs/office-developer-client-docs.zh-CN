---
title: Append 方法 (ADOX Users)
TOCTitle: Append Method (ADOX Users)
ms:assetid: b7a1128b-c6e7-2071-c914-913b6bd245ae
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249884(v=office.15)
ms:contentKeyID: 48547302
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 948ba15ccca5dabe6b4cb75c09f7e47e65994b2b
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25887766"
---
# <a name="append-method-adox-users"></a><span data-ttu-id="cea38-102">Append 方法 (ADOX Users)</span><span class="sxs-lookup"><span data-stu-id="cea38-102">Append Method (ADOX Users)</span></span>


<span data-ttu-id="cea38-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="cea38-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="cea38-104">将新的 [User](user-object-adox.md) 对象添加到 [Users](users-collection-adox.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="cea38-104">Adds a new [User](user-object-adox.md) object to the [Users](users-collection-adox.md) collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="cea38-105">语法</span><span class="sxs-lookup"><span data-stu-id="cea38-105">Syntax</span></span>

<span data-ttu-id="cea38-106">*用户*。追加*用户*\[，*密码*\]</span><span class="sxs-lookup"><span data-stu-id="cea38-106">*Users*.Append*User*\[,*Password*\]</span></span>

## <a name="parameters"></a><span data-ttu-id="cea38-107">参数</span><span class="sxs-lookup"><span data-stu-id="cea38-107">Parameters</span></span>

  - <span data-ttu-id="cea38-108">*User*</span><span class="sxs-lookup"><span data-stu-id="cea38-108">*User*</span></span>

  - <span data-ttu-id="cea38-109">一个 **Variant** 值，包含对要追加的 **User** 对象的引用，或者是要创建并追加的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="cea38-109">A **Variant** value that contains the **User** object to append or the name of the user to create and append.</span></span>

  - <span data-ttu-id="cea38-110">*Password*</span><span class="sxs-lookup"><span data-stu-id="cea38-110">*Password*</span></span>

  - <span data-ttu-id="cea38-111">可选。</span><span class="sxs-lookup"><span data-stu-id="cea38-111">Optional.</span></span> <span data-ttu-id="cea38-112">包含该用户的密码的 **String** 值。</span><span class="sxs-lookup"><span data-stu-id="cea38-112">A **String** value that contains the password for the user.</span></span> <span data-ttu-id="cea38-113">*Password*参数对应于指定的**用户**对象的[ChangePassword](changepassword-method-adox.md)方法的值。</span><span class="sxs-lookup"><span data-stu-id="cea38-113">The *Password* parameter corresponds to the value specified by the [ChangePassword](changepassword-method-adox.md) method of a **User** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="cea38-114">说明</span><span class="sxs-lookup"><span data-stu-id="cea38-114">Remarks</span></span>

<span data-ttu-id="cea38-p102">**Catalog** 的 [Users](catalog-object-adox.md) 集合表示该目录的所有用户。 **Group** 的 [Users](group-object-adox.md) 集合仅表示在该特定组中有成员资格的用户。</span><span class="sxs-lookup"><span data-stu-id="cea38-p102">The **Users** collection of a [Catalog](catalog-object-adox.md) represents all the catalog's users. The **Users** collection for a [Group](group-object-adox.md) represents only the users that have a membership in the specific group.</span></span>

<span data-ttu-id="cea38-117">如果提供程序不支持创建用户，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="cea38-117">An error will occur if the provider does not support creating users.</span></span>


> [!NOTE]
> <span data-ttu-id="cea38-118">[!注释] 在将 **User** 对象追加到 **Group** 对象的 **Users** 集合之前， **Catalog** 的 [Users](name-property-adox.md) 集合中必须存在具有与要追加的 **User** 对象相同 **Name** 的 User 对象。</span><span class="sxs-lookup"><span data-stu-id="cea38-118">Before appending a **User** object to the **Users** collection of a **Group** object, a **User** object with the same [Name](name-property-adox.md) as the one to be appended must already exist in the **Users** collection of the **Catalog**.</span></span>


