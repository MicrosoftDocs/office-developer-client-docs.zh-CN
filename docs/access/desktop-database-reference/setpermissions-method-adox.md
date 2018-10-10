---
title: SetPermissions 方法 (ADOX)
TOCTitle: SetPermissions Method (ADOX)
ms:assetid: 63d1053d-fb32-456b-ae67-3a4e45aa01af
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249382(v=office.15)
ms:contentKeyID: 48545274
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 35578de28509e510e9ba5329cfdabc2eff8207b1
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468005"
---
# <a name="setpermissions-method-adox"></a><span data-ttu-id="d2f45-102">SetPermissions 方法 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="d2f45-102">SetPermissions Method (ADOX)</span></span>


<span data-ttu-id="d2f45-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="d2f45-103">**Applies to**: Access 2013 | Office 2013</span></span>



<span data-ttu-id="d2f45-104">指定组或用户对某个对象的权限。</span><span class="sxs-lookup"><span data-stu-id="d2f45-104">Specifies the permissions for a group or user on an object.</span></span>

## <a name="syntax"></a><span data-ttu-id="d2f45-105">语法</span><span class="sxs-lookup"><span data-stu-id="d2f45-105">Syntax</span></span>

<span data-ttu-id="d2f45-106">*GroupOrUser*。SetPermissions*名称*， *ObjectType*，*操作*、*权限* \[，*继承*\] \[，*ObjectTypeId*\]</span><span class="sxs-lookup"><span data-stu-id="d2f45-106">*GroupOrUser*.SetPermissions*Name*, *ObjectType*, *Action*, *Rights* \[,*Inherit*\] \[,*ObjectTypeId*\]</span></span>

## <a name="parameters"></a><span data-ttu-id="d2f45-107">参数</span><span class="sxs-lookup"><span data-stu-id="d2f45-107">Parameters</span></span>

  - <span data-ttu-id="d2f45-108">*Name*</span><span class="sxs-lookup"><span data-stu-id="d2f45-108">*Name*</span></span>

  - <span data-ttu-id="d2f45-109">**String** 值，指定设置权限所针对的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="d2f45-109">A **String** value that specifies the name of the object for which to set permissions.</span></span>

  - <span data-ttu-id="d2f45-110">*ObjectType*</span><span class="sxs-lookup"><span data-stu-id="d2f45-110">*ObjectType*</span></span>

  - <span data-ttu-id="d2f45-111">一个类型为 **Long** 的值，可以是 [ObjectTypeEnum](objecttypeenum.md) 常量中的一个，用于指定要为其获取权限的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="d2f45-111">A **Long** value which can be one of the [ObjectTypeEnum](objecttypeenum.md) constants, that specifies the type of the object for which to get permissions.</span></span>

  - <span data-ttu-id="d2f45-112">*Action*</span><span class="sxs-lookup"><span data-stu-id="d2f45-112">*Action*</span></span>

  - <span data-ttu-id="d2f45-113">一个可设为 **ActionEnum** 常量之一的 [Long](actionenum.md) 值，指定设置权限时要执行的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="d2f45-113">A **Long** value which can be one of the [ActionEnum](actionenum.md) constants that specifies the type of action to perform when setting permissions.</span></span>

  - <span data-ttu-id="d2f45-114">*Rights*</span><span class="sxs-lookup"><span data-stu-id="d2f45-114">*Rights*</span></span>

  - <span data-ttu-id="d2f45-115">**Long** 值，可以是一个或多个 [RightsEnum](rightsenum.md) 常量的位掩码，该值表示要设置的权限。</span><span class="sxs-lookup"><span data-stu-id="d2f45-115">A **Long** value which can be a bitmask of one or more of the [RightsEnum](rightsenum.md) constants, that indicates the rights to set.</span></span>

  - <span data-ttu-id="d2f45-116">*Inherit*</span><span class="sxs-lookup"><span data-stu-id="d2f45-116">*Inherit*</span></span>

  - <span data-ttu-id="d2f45-p101">可选。一个可设为 **InheritTypeEnum** 常量之一的 [Long](inherittypeenum.md) 值，指定对象如何继承这些权限。默认值为 **adInheritNone** 。</span><span class="sxs-lookup"><span data-stu-id="d2f45-p101">Optional. A **Long** value which can be one of the [InheritTypeEnum](inherittypeenum.md) constants, that specifies how objects will inherit these permissions. The default value is **adInheritNone**.</span></span>

  - <span data-ttu-id="d2f45-120">*ObjectTypeId*</span><span class="sxs-lookup"><span data-stu-id="d2f45-120">*ObjectTypeId*</span></span>

  - <span data-ttu-id="d2f45-121">可选。</span><span class="sxs-lookup"><span data-stu-id="d2f45-121">Optional.</span></span> <span data-ttu-id="d2f45-122">**Variant** 值，指定 OLE DB 规范未定义的提供程序对象类型的 GUID。</span><span class="sxs-lookup"><span data-stu-id="d2f45-122">A **Variant** value that specifies the GUID for a provider object type not defined by the OLE DB specification.</span></span> <span data-ttu-id="d2f45-123">此参数是必需的如果将*ObjectType*设置为**adPermObjProviderSpecific**;否则，它将不使用。</span><span class="sxs-lookup"><span data-stu-id="d2f45-123">This parameter is required if *ObjectType* is set to **adPermObjProviderSpecific**; otherwise, it is not used.</span></span>

## <a name="remarks"></a><span data-ttu-id="d2f45-124">说明</span><span class="sxs-lookup"><span data-stu-id="d2f45-124">Remarks</span></span>

<span data-ttu-id="d2f45-125">如果提供程序不支持为组或用户设置访问权限，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="d2f45-125">An error will occur if the provider does not support setting access rights for groups or users.</span></span>


> [!NOTE]
> <P><span data-ttu-id="d2f45-126">在调用<STRONG>SetPermissions</STRONG>时，将操作设置为<STRONG>adAccessRevoke</STRONG>重写<EM>权限</EM>参数的任何设置。</span><span class="sxs-lookup"><span data-stu-id="d2f45-126">When calling <STRONG>SetPermissions</STRONG>, setting Actions to <STRONG>adAccessRevoke</STRONG> overrides any settings of the <EM>Rights</EM> parameter.</span></span> <span data-ttu-id="d2f45-127">不要对<STRONG>adAccessRevoke</STRONG>设置<EM>操作</EM>，如果您希望<EM>权限</EM>参数中指定的权限，才能生效。</span><span class="sxs-lookup"><span data-stu-id="d2f45-127">Do not set <EM>Actions</EM> to <STRONG>adAccessRevoke</STRONG> if you want the rights specified in the <EM>Rights</EM> parameter to take effect.</span></span></P>


