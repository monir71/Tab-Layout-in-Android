User defined ViewPagerMessengerAdapter class is important here.

        public class ViewPagerMessengerAdapter extends FragmentPagerAdapter{
        
            public ViewPagerMessengerAdapter(@NonNull FragmentManager fm) {
                super(fm);
            }
        
            @NonNull
            @Override
            public Fragment getItem(int position) {
                if(position == 0)
                    return new ChatFragment();
                else if (position == 1)
                    return new CallsFragment();
                    else
                        return new StatusFragment();
            }
        
            @Override
            public int getCount() {
                return 3;
            }
        
            @Nullable
            @Override
            public CharSequence getPageTitle(int position) {
                if(position == 0)
                    return "Chat";
                else if (position == 1)
                    return "Call";
                else
                    return "Status";
            }
        }

Now connects Fragments and ViewPager

        ViewPagerMessengerAdapter adapter = new ViewPagerMessengerAdapter(getSupportFragmentManager());
        viewPager.setAdapter(adapter);

        tab.setupWithViewPager(viewPager);
