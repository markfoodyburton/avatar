# avatar
an avatar for HUBS


First get your ingredients
You will need Blender https://www.blender.org/
  (I'm using v2.90.1)
and an addon to Blender https://github.com/MozillaReality/hubs-blender-exporter

You will also need the starter robot file:
https://github.com/MozillaReality/hubs-avatar-pipelines/blob/master/Blender/AvatarBot/AvatarBot_base_for_export.blend

Open this file in Blender. You may remove all the body, leaving just the bones/armature.

visit: https://webdemo.avatarsdk.com/
and build an avatar of your choice
Use a good picture of a head, your own or one you would like to be!

Download the 1.2 version

in Blender, and "file/import" the model/model.obj

Find a shirt, polo or t-shirt from https://free3d.com/
Download, and import that into Blender

Now in Blender, move all the parts to the right place.
Dont move the bones yet, and make sure the eye's are on the same level as the eye bones

Reduce the vertex's in the models as much as you can bare, using the decimate modifier (in object mode, under modifiers)
 When you are happy, on the pull down menu, use apply !

When all the elements are as you want them - make sure the origin of the model (tiny orange dot) is at the base of the skeliton. To do that, with all objects selected hit ctrl-A and "all transforms".

Shrink the eye bones into the eye sockets, so that the eye's will rotate correctly.
For each eye, in edit mode select a face in the eyeball, and then using 'l' select all the linked faces in the eyeball, also select a the eyelid
Make a new virtex group for each eye, make sure you call the group the same name as the bone with the same name

Make a new virtex group for all of the other bones in the body (that you care about - at a minimum the head, neck and spine)

Merge the models so you have one model (click one, then shift click the other, then press 'ctrl-j' to join them)
Move the model inside the AvatarRoot - select the avatarRoot, then shift select the model, then in the viewport hit Ctrl-P
Connect the bones - connect model and then AvatarRoot, then Ctrl-P, then select Aramture Deform

Theoretically the animations should now work. You should be able to 'play' the animations associated with the eyes for instance.

To export this model, make sure that at the top level, in the object properties menu, you add a Hubs extension for loop-animation, with "idle_eyes" as the clip name.

You can then export the model as a gITF (make sure the hubs extension is enabled)

To add a mouth movement
In object mode, add a basic and a 'mouthOpen' shape key. Set the value to 1, and then move the mesh for a wide open mouth.
Set the value back to 0, and select 'Basic'
Onthe model's object property, add a Hubs component, "morph-audio-feedback", and the name should be mouthOpen
  (NB there should be only this hubs component on the model, on the collection there should be the other hubs component for the eyes)














