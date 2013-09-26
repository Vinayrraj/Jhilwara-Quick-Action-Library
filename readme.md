
How to Use
==========

1. Create Action item:
	ActionItem actItem = new ActionItem(ACTION_ID, "String Name", getResources().getDrawable(R.drawable.icon));
        //use setSticky(true) to disable QuickAction dialog being dismissed after an item is clicked
        actItem.setSticky(true);

2. Create QuickAction:
	final QuickAction quickAction = new QuickAction(this, QuickAction.VERTICAL);

3. Add Action item:
	quickAction.addActionItem(actItem);

4. Attach Listener
	quickAction.setOnActionItemClickListener(new QuickAction.OnActionItemClickListener() {			
				@Override
				public void onItemClick(QuickAction source, int pos, int actionId) {
					//here we can filter which action item was clicked with pos or actionId parameter
					ActionItem actionItem = quickAction.getActionItem(pos);
                 
					Toast.makeText(getApplicationContext(), actionItem.getTitle() + " selected", Toast.LENGTH_SHORT).show();			    
				}
			});
		
			//set listnener for on dismiss event, this listener will be called only if QuickAction dialog was dismissed
			//by clicking the area outside the dialog.
			quickAction.setOnDismissListener(new QuickAction.OnDismissListener() {			
				@Override
				public void onDismiss() {
					Toast.makeText(getApplicationContext(), "Dismissed", Toast.LENGTH_SHORT).show();
				}
			});

5. Show 
	quickAction.show(v);


Modified by
============
vinayrraj@gmail.com


Created by
============
* Lorensius W. L. T - <lorenz@londatiga.net>
* Kevin Peck - <kevinwpeck@gmail.com>

