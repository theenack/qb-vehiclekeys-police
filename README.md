# qb-vehiclekeys-police
Unlock command for police


## add this into your qb-vehiclekeys >> client.lua


RegisterNetEvent('vehiclekeys:client:PoliceUnlock') AddEventHandler('vehiclekeys:client:PoliceUnlock', function()     local ped = PlayerPedId()     local pos = GetEntityCoords(ped)     local vehicle = QBCore.Functions.GetClosestVehicle(pos)     SetVehicleDoorsLocked(vehicle, 0)     SetVehicleAlarm(vehicle, false)     SetVehicleDoorsLockedForAllPlayers(vehicle, false)     lockpicked = true     QBCore.Functions.Notify('Opened Door!', 'success')     TriggerEvent('vehiclekeys:client:SetOwner', GetVehicleNumberPlateText(vehicle))  end)     


##and add this into police radial menu

                   {                     id = 'unlock',                     title = 'Unlock Veh',                     icon = 'user-lock',                     type = 'client',                     event = 'vehiclekeys:client:PoliceUnlock',                     shouldClose = true                 },