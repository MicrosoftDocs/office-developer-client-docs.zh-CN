---
title: Append 方法 (ADOX Groups)
TOCTitle: Append Method (ADOX Groups)
ms:assetid: c3245a24-55b8-3f3f-1c4a-43a119d84dc8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249954(v=office.15)
ms:contentKeyID: 48547567
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 76c602896a629881d06a3f3cf80326e02340186e
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468572"
---
# <a name="append-method-adox-groups"></a><span data-ttu-id="dfb55-102">Append 方法 (ADOX Groups)</span><span class="sxs-lookup"><span data-stu-id="dfb55-102">Append Method (ADOX Groups)</span></span>


<span data-ttu-id="dfb55-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="dfb55-103">**Applies to**: Access 2013 | Office 2013</span></span>



<span data-ttu-id="dfb55-104">将新的 [Group](group-object-adox.md) 对象添加到 [Groups](groups-collection-adox.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="dfb55-104">Adds a new [Group](group-object-adox.md) object to the [Groups](groups-collection-adox.md) collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="dfb55-105">语法</span><span class="sxs-lookup"><span data-stu-id="dfb55-105">Syntax</span></span>

<span data-ttu-id="dfb55-106">*组*。追加*组*</span><span class="sxs-lookup"><span data-stu-id="dfb55-106">*Groups*.Append*Group*</span></span>

## <a name="parameters"></a><span data-ttu-id="dfb55-107">参数</span><span class="sxs-lookup"><span data-stu-id="dfb55-107">Parameters</span></span>

  - <span data-ttu-id="dfb55-108">*Group*</span><span class="sxs-lookup"><span data-stu-id="dfb55-108">*Group*</span></span>

  - <span data-ttu-id="dfb55-109">要追加的 **Group** 对象，或者要创建并追加的组的名称。</span><span class="sxs-lookup"><span data-stu-id="dfb55-109">The **Group** object to append or the name of the group to create and append.</span></span>

## <a name="remarks"></a><span data-ttu-id="dfb55-110">备注</span><span class="sxs-lookup"><span data-stu-id="dfb55-110">Remarks</span></span>

<span data-ttu-id="dfb55-p101">**Catalog** 的 [Groups](catalog-object-adox.md) 集合表示该目录的所有组帐户。 **User** 的 [Groups](user-object-adox.md) 集合仅表示该用户所属的组。</span><span class="sxs-lookup"><span data-stu-id="dfb55-p101">The **Groups** collection of a [Catalog](catalog-object-adox.md) represents all of the catalog's group accounts. The **Groups** collection for a [User](user-object-adox.md) represents only the group to which the user belongs.</span></span>

<span data-ttu-id="dfb55-113">如果提供程序不支持创建组，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="dfb55-113">An error will occur if the provider does not support creating groups.</span></span>


> [!NOTE]
> <P><span data-ttu-id="dfb55-114">[!注释] 在将 <STRONG>Group</STRONG> 对象追加到 <STRONG>User</STRONG> 对象的 <STRONG>Groups</STRONG> 集合之前， <STRONG>Catalog</STRONG> 的 <A href="name-property-adox.md">Groups</A> 集合中必须存在具有与要追加的 <STRONG>Group</STRONG> 对象相同 <STRONG>Name</STRONG> 的 Group 对象。</span><span class="sxs-lookup"><span data-stu-id="dfb55-114">Before appending a <STRONG>Group</STRONG> object to the <STRONG>Groups</STRONG> collection of a <STRONG>User</STRONG> object, a <STRONG>Group</STRONG> object with the same <A href="name-property-adox.md">Name</A> as the one to be appended must already exist in the <STRONG>Groups</STRONG> collection of the <STRONG>Catalog</STRONG>.</span></span></P>


