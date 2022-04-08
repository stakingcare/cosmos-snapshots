# Umee snapshot install guide

## Step 1 - Stop Umee service

```
systemctl stop umeed.service

```

## Step 2 - Delete old data

```
rm -rf ~/.umee/data; \
mkdir -p ~/.umee/data; \
cd ~/.umee/data

```

## Step 3 - Download snapshot

```
LATEST_SNAPSHOT=$(curl -s https://snapshots.stakingcare.com/umee/ | egrep -o ">umee.*tar" | tr -d ">" | tail -n1)
wget -O - https://snapshots.stakingcare.com/umee/${LATEST_SNAPSHOT} | tar xf -

```

## Step 4 -  Start Umee service

```
systemctl start umeed.service

```

