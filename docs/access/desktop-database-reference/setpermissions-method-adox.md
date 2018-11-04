---
title: SetPermissions 方法 (ADOX)
TOCTitle: SetPermissions method (ADOX)
ms:assetid: 63d1053d-fb32-456b-ae67-3a4e45aa01af
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249382(v=office.15)
ms:contentKeyID: 48545274
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b9ea1c08223282654af636326ba9a8c2bfe70e67
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949598"
---
# <a name="setpermissions-method-adox"></a><span data-ttu-id="955bc-102">SetPermissions 方法 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="955bc-102">SetPermissions method (ADOX)</span></span>

<span data-ttu-id="955bc-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="955bc-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="955bc-104">指定组或用户对某个对象的权限。</span><span class="sxs-lookup"><span data-stu-id="955bc-104">Specifies the permissions for a group or user on an object.</span></span>

## <a name="syntax"></a><span data-ttu-id="955bc-105">语法</span><span class="sxs-lookup"><span data-stu-id="955bc-105">Syntax</span></span>

<span data-ttu-id="955bc-106">*GroupOrUser*。SetPermissions*名称*， *ObjectType*，*操作*、*权限* \[，*继承*\] \[，*ObjectTypeId*\]</span><span class="sxs-lookup"><span data-stu-id="955bc-106">*GroupOrUser*.SetPermissions*Name*, *ObjectType*, *Action*, *Rights* \[,*Inherit*\] \[,*ObjectTypeId*\]</span></span>

## <a name="parameters"></a><span data-ttu-id="955bc-107">参数</span><span class="sxs-lookup"><span data-stu-id="955bc-107">Parameters</span></span>

|<span data-ttu-id="955bc-108">参数</span><span class="sxs-lookup"><span data-stu-id="955bc-108">Parameter</span></span>|<span data-ttu-id="955bc-109">说明</span><span class="sxs-lookup"><span data-stu-id="955bc-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="955bc-110">*Name*</span><span class="sxs-lookup"><span data-stu-id="955bc-110">*Name*</span></span> |<span data-ttu-id="955bc-111">**String** 值，指定设置权限所针对的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="955bc-111">A **String** value that specifies the name of the object for which to set permissions.</span></span>|
|<span data-ttu-id="955bc-112">*ObjectType*</span><span class="sxs-lookup"><span data-stu-id="955bc-112">*ObjectType*</span></span> |<span data-ttu-id="955bc-113">一个类型为 **Long** 的值，可以是 [ObjectTypeEnum](objecttypeenum.md) 常量中的一个，用于指定要为其获取权限的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="955bc-113">A **Long** value which can be one of the [ObjectTypeEnum](objecttypeenum.md) constants, that specifies the type of the object for which to get permissions.</span></span>|
|<span data-ttu-id="955bc-114">*Action*</span><span class="sxs-lookup"><span data-stu-id="955bc-114">*Action*</span></span> |<span data-ttu-id="955bc-115">一个可设为 **ActionEnum** 常量之一的 [Long](actionenum.md) 值，指定设置权限时要执行的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="955bc-115">A **Long** value which can be one of the [ActionEnum](actionenum.md) constants that specifies the type of action to perform when setting permissions.</span></span>|
|<span data-ttu-id="955bc-116">*Rights*</span><span class="sxs-lookup"><span data-stu-id="955bc-116">*Rights*</span></span> |<span data-ttu-id="955bc-117">**Long** 值，可以是一个或多个 [RightsEnum](rightsenum.md) 常量的位掩码，该值表示要设置的权限。</span><span class="sxs-lookup"><span data-stu-id="955bc-117">A **Long** value which can be a bitmask of one or more of the [RightsEnum](rightsenum.md) constants, that indicates the rights to set.</span></span>|
|<span data-ttu-id="955bc-118">*Inherit*</span><span class="sxs-lookup"><span data-stu-id="955bc-118">*Inherit*</span></span> |<span data-ttu-id="955bc-p101">可选。一个可设为 **InheritTypeEnum** 常量之一的 [Long](inherittypeenum.md) 值，指定对象如何继承这些权限。默认值为 **adInheritNone** 。</span><span class="sxs-lookup"><span data-stu-id="955bc-p101">Optional. A **Long** value which can be one of the [InheritTypeEnum](inherittypeenum.md) constants, that specifies how objects will inherit these permissions. The default value is **adInheritNone**.</span></span>|
|<span data-ttu-id="955bc-122">*ObjectTypeId*</span><span class="sxs-lookup"><span data-stu-id="955bc-122">*ObjectTypeId*</span></span> |<span data-ttu-id="955bc-123">可选。</span><span class="sxs-lookup"><span data-stu-id="955bc-123">Optional.</span></span> <span data-ttu-id="955bc-124">**Variant** 值，指定 OLE DB 规范未定义的提供程序对象类型的 GUID。</span><span class="sxs-lookup"><span data-stu-id="955bc-124">A **Variant** value that specifies the GUID for a provider object type not defined by the OLE DB specification.</span></span> <span data-ttu-id="955bc-125">此参数是必需的如果将*ObjectType*设置为**adPermObjProviderSpecific**;否则，它将不使用。</span><span class="sxs-lookup"><span data-stu-id="955bc-125">This parameter is required if *ObjectType* is set to **adPermObjProviderSpecific**; otherwise, it is not used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="955bc-126">说明</span><span class="sxs-lookup"><span data-stu-id="955bc-126">Remarks</span></span>

<span data-ttu-id="955bc-127">如果提供程序不支持为组或用户设置访问权限，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="955bc-127">An error will occur if the provider does not support setting access rights for groups or users.</span></span>

> [!NOTE]
> <span data-ttu-id="955bc-128">在调用**SetPermissions**时，将操作设置为**adAccessRevoke**重写*权限*参数的任何设置。</span><span class="sxs-lookup"><span data-stu-id="955bc-128">When calling **SetPermissions**, setting Actions to **adAccessRevoke** overrides any settings of the *Rights* parameter.</span></span> <span data-ttu-id="955bc-129">不要对**adAccessRevoke**设置*操作*，如果您希望*权限*参数中指定的权限，才能生效。</span><span class="sxs-lookup"><span data-stu-id="955bc-129">Do not set *Actions* to **adAccessRevoke** if you want the rights specified in the *Rights* parameter to take effect.</span></span>


